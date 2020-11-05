---
ms.date: 07/23/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
description: Ресурсы DSC предоставляют шаблоны для настройки DSC. В ресурсе представлены свойства, которые можно настроить (схема), и функции скриптов PowerShell, которые использует локальный диспетчер конфигураций (LCM) для применения конфигурации.
ms.openlocfilehash: 1634db84deff8de3b33c941ad738dc21cf3017ac
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658444"
---
# <a name="dsc-resources"></a><span data-ttu-id="f1726-105">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="f1726-105">DSC Resources</span></span>

> <span data-ttu-id="f1726-106">Относится к Windows PowerShell 4.0 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="f1726-106">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="f1726-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="f1726-107">Overview</span></span>

<span data-ttu-id="f1726-108">Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="f1726-108">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="f1726-109">В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).</span><span class="sxs-lookup"><span data-stu-id="f1726-109">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="f1726-110">Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="f1726-110">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="f1726-111">Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f1726-111">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="f1726-112">Каждый ресурс содержит \*схему, которая определяет синтаксис, используемый ресурсом при [конфигурации](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f1726-112">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="f1726-113">Схема ресурса может быть определена следующими способами.</span><span class="sxs-lookup"><span data-stu-id="f1726-113">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="f1726-114">Файл `Schema.Mof`. Большинство ресурсов определяет свою _схему_ в файле `schema.mof` с помощью [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="f1726-114">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="f1726-115">Файл `<Resource Name>.schema.psm1`. [Составные ресурсы](../configurations/compositeConfigs.md) определяют свою _схему_ в файле `<ResourceName>.schema.psm1` с помощью [блока параметров](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="f1726-115">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters).</span></span>
- <span data-ttu-id="f1726-116">Файл `<Resource Name>.psm1`. Ресурсы DSC, основанные на классе, определяют свою _схему_ в описании класса.</span><span class="sxs-lookup"><span data-stu-id="f1726-116">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="f1726-117">Элементы синтаксиса обозначаются как свойства класса.</span><span class="sxs-lookup"><span data-stu-id="f1726-117">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="f1726-118">Дополнительные сведения см. в статье [About Classes and Desired State Configuration](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc) (О классах и настройке требуемого состояния).</span><span class="sxs-lookup"><span data-stu-id="f1726-118">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="f1726-119">Чтобы получить синтаксис из ресурса DSC, используйте командлет [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) с параметром **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="f1726-119">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="f1726-120">Это похоже на использование командлета [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с параметром **Syntax** для получения синтаксиса командлета.</span><span class="sxs-lookup"><span data-stu-id="f1726-120">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="f1726-121">В выходных данных будет показан шаблон, используемый в указанном блоке ресурса.</span><span class="sxs-lookup"><span data-stu-id="f1726-121">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="f1726-122">Выходные данные должны соответствовать выходным данным, приведенным ниже, так как в будущем этот ресурс может измениться.</span><span class="sxs-lookup"><span data-stu-id="f1726-122">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="f1726-123">Например, синтаксис командлета, для которого _ключи_ в квадратных скобках являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="f1726-123">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="f1726-124">Типы указывают типы данных для каждого ключа в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="f1726-124">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="f1726-125">Ключ **Ensure** является необязательным, так как Present является его значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1726-125">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

> [!NOTE]
> <span data-ttu-id="f1726-126">В версиях PowerShell до 7.0 `Get-DscResource` не находит ресурсы DSC на основе класса.</span><span class="sxs-lookup"><span data-stu-id="f1726-126">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="f1726-127">Блок ресурсов **Служба** внутри конфигурации может выглядеть следующим образом. Это необходимо, чтобы **убедиться** , что служба подсистемы печати работает.</span><span class="sxs-lookup"><span data-stu-id="f1726-127">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="f1726-128">Перед использованием ресурса в конфигурации его необходимо импортировать с помощью командлета [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="f1726-128">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the
    # resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as l
        # ong as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

<span data-ttu-id="f1726-129">Конфигурации могут содержать несколько экземпляров одного типа ресурса.</span><span class="sxs-lookup"><span data-stu-id="f1726-129">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="f1726-130">Имя каждого экземпляра должно быть уникально.</span><span class="sxs-lookup"><span data-stu-id="f1726-130">Each instance must be uniquely named.</span></span> <span data-ttu-id="f1726-131">В следующем примере второй блок ресурсов **Служба** добавляется для настройки службы DHCP.</span><span class="sxs-lookup"><span data-stu-id="f1726-131">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the
    # resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as
        # long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service
        # resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="f1726-132">Начиная с PowerShell 5.0, технология IntelliSense включена в DSC.</span><span class="sxs-lookup"><span data-stu-id="f1726-132">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="f1726-133">Новая функция позволяет использовать клавиши <kbd>TAB</kbd> и <kbd>CTRL</kbd>+<kbd>ПРОБЕЛ</kbd> для автозаполнения имен ключей.</span><span class="sxs-lookup"><span data-stu-id="f1726-133">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Технология IntelliSense с использованием заполнения нажатием клавиши TAB](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="f1726-135">Типы ресурсов</span><span class="sxs-lookup"><span data-stu-id="f1726-135">Types of resources</span></span>

<span data-ttu-id="f1726-136">В Windows имеются встроенные ресурсы. Кроме того, существуют ресурсы для ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="f1726-136">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="f1726-137">Имеются ресурсы для [межузловых зависимостей](../configurations/crossNodeDependencies.md), ресурсы для управления пакетами, а также [ресурсы, принадлежащие сообществу и поддерживаемые им](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="f1726-137">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="f1726-138">Шаги, описанные выше, можно использовать для определения синтаксиса этих ресурсов и способов их использования.</span><span class="sxs-lookup"><span data-stu-id="f1726-138">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="f1726-139">Страницы, на которых было описано использование этих ресурсов, собраны в разделе **Справочные материалы**.</span><span class="sxs-lookup"><span data-stu-id="f1726-139">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="f1726-140">Встроенные ресурсы Windows</span><span class="sxs-lookup"><span data-stu-id="f1726-140">Windows built-in resources</span></span>

- [<span data-ttu-id="f1726-141">Ресурс Archive</span><span class="sxs-lookup"><span data-stu-id="f1726-141">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="f1726-142">Ресурс Environment</span><span class="sxs-lookup"><span data-stu-id="f1726-142">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="f1726-143">Ресурс File</span><span class="sxs-lookup"><span data-stu-id="f1726-143">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="f1726-144">Ресурс Group</span><span class="sxs-lookup"><span data-stu-id="f1726-144">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="f1726-145">Ресурс GroupSet</span><span class="sxs-lookup"><span data-stu-id="f1726-145">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="f1726-146">Ресурс Log</span><span class="sxs-lookup"><span data-stu-id="f1726-146">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="f1726-147">Ресурс Package</span><span class="sxs-lookup"><span data-stu-id="f1726-147">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="f1726-148">Ресурс ProcessSet</span><span class="sxs-lookup"><span data-stu-id="f1726-148">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="f1726-149">Ресурс Registry</span><span class="sxs-lookup"><span data-stu-id="f1726-149">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="f1726-150">Ресурс Script</span><span class="sxs-lookup"><span data-stu-id="f1726-150">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="f1726-151">Ресурс Service</span><span class="sxs-lookup"><span data-stu-id="f1726-151">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="f1726-152">Ресурс ServiceSet</span><span class="sxs-lookup"><span data-stu-id="f1726-152">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="f1726-153">Ресурс User</span><span class="sxs-lookup"><span data-stu-id="f1726-153">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="f1726-154">Ресурс WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="f1726-154">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="f1726-155">Ресурс WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="f1726-155">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="f1726-156">Ресурс WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="f1726-156">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="f1726-157">Ресурс WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="f1726-157">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="f1726-158">Ресурс WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="f1726-158">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="f1726-159">Ресурс WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="f1726-159">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="f1726-160">Ресурсы межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="f1726-160">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="f1726-161">Ресурс WaitForAll</span><span class="sxs-lookup"><span data-stu-id="f1726-161">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="f1726-162">Ресурс WaitForSome</span><span class="sxs-lookup"><span data-stu-id="f1726-162">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="f1726-163">Ресурс WaitForAny</span><span class="sxs-lookup"><span data-stu-id="f1726-163">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="f1726-164">Ресурсы управления пакетами</span><span class="sxs-lookup"><span data-stu-id="f1726-164">Package Management resources</span></span>

- [<span data-ttu-id="f1726-165">Ресурс PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f1726-165">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="f1726-166">Ресурс PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="f1726-166">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="f1726-167">Ресурсы Linux</span><span class="sxs-lookup"><span data-stu-id="f1726-167">Linux resources</span></span>

- [<span data-ttu-id="f1726-168">Ресурс Linux Archive</span><span class="sxs-lookup"><span data-stu-id="f1726-168">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- <span data-ttu-id="f1726-169">Ресурс [Linux Environment](../reference/resources/linux/lnxEnvironmentResource.md)</span><span class="sxs-lookup"><span data-stu-id="f1726-169">[Linux Environment Resource](../reference/resources/linux/lnxEnvironmentResource.md)</span></span>
- [<span data-ttu-id="f1726-170">Ресурс Linux FileLine</span><span class="sxs-lookup"><span data-stu-id="f1726-170">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="f1726-171">Ресурс Linux File</span><span class="sxs-lookup"><span data-stu-id="f1726-171">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="f1726-172">Ресурс Linux Group</span><span class="sxs-lookup"><span data-stu-id="f1726-172">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="f1726-173">Ресурс Linux Package</span><span class="sxs-lookup"><span data-stu-id="f1726-173">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="f1726-174">Ресурс Linux Script</span><span class="sxs-lookup"><span data-stu-id="f1726-174">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="f1726-175">Ресурс Linux Service</span><span class="sxs-lookup"><span data-stu-id="f1726-175">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="f1726-176">Ресурс Linux SshAuthorizedKeys</span><span class="sxs-lookup"><span data-stu-id="f1726-176">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="f1726-177">Ресурс Linux User</span><span class="sxs-lookup"><span data-stu-id="f1726-177">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
