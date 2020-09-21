---
ms.date: 07/23/2020
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
ms.openlocfilehash: 6ab831c9d423c6189951b43bfab92f800366ceca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87777925"
---
# <a name="dsc-resources"></a><span data-ttu-id="d2611-103">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="d2611-103">DSC Resources</span></span>

> <span data-ttu-id="d2611-104">Относится к Windows PowerShell 4.0 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="d2611-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="d2611-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="d2611-105">Overview</span></span>

<span data-ttu-id="d2611-106">Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="d2611-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="d2611-107">В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).</span><span class="sxs-lookup"><span data-stu-id="d2611-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="d2611-108">Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="d2611-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="d2611-109">Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d2611-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="d2611-110">Каждый ресурс содержит \*схему, которая определяет синтаксис, используемый ресурсом при [конфигурации](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d2611-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="d2611-111">Схема ресурса может быть определена следующими способами.</span><span class="sxs-lookup"><span data-stu-id="d2611-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="d2611-112">Файл `Schema.Mof`. Большинство ресурсов определяет свою _схему_ в файле `schema.mof` с помощью [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="d2611-112">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="d2611-113">Файл `<Resource Name>.schema.psm1`. [Составные ресурсы](../configurations/compositeConfigs.md) определяют свою _схему_ в файле `<ResourceName>.schema.psm1` с помощью [блока параметров](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="d2611-113">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="d2611-114">Файл `<Resource Name>.psm1`. Ресурсы DSC, основанные на классе, определяют свою _схему_ в описании класса.</span><span class="sxs-lookup"><span data-stu-id="d2611-114">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="d2611-115">Элементы синтаксиса обозначаются как свойства класса.</span><span class="sxs-lookup"><span data-stu-id="d2611-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="d2611-116">Дополнительные сведения см. в статье [About Classes and Desired State Configuration](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc) (О классах и настройке требуемого состояния).</span><span class="sxs-lookup"><span data-stu-id="d2611-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="d2611-117">Чтобы получить синтаксис из ресурса DSC, используйте командлет [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) с параметром **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="d2611-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="d2611-118">Это похоже на использование командлета [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с параметром **Syntax** для получения синтаксиса командлета.</span><span class="sxs-lookup"><span data-stu-id="d2611-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="d2611-119">В выходных данных будет показан шаблон, используемый в указанном блоке ресурса.</span><span class="sxs-lookup"><span data-stu-id="d2611-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="d2611-120">Выходные данные должны соответствовать выходным данным, приведенным ниже, так как в будущем этот ресурс может измениться.</span><span class="sxs-lookup"><span data-stu-id="d2611-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="d2611-121">Например, синтаксис командлета, для которого _ключи_ в квадратных скобках являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="d2611-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="d2611-122">Типы указывают типы данных для каждого ключа в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="d2611-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="d2611-123">Ключ **Ensure** является необязательным, так как Present является его значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2611-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

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
> <span data-ttu-id="d2611-124">В версиях PowerShell до 7.0 `Get-DscResource` не находит ресурсы DSC на основе класса.</span><span class="sxs-lookup"><span data-stu-id="d2611-124">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="d2611-125">Блок ресурсов **Служба** внутри конфигурации может выглядеть следующим образом. Это необходимо, чтобы **убедиться**, что служба подсистемы печати работает.</span><span class="sxs-lookup"><span data-stu-id="d2611-125">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="d2611-126">Перед использованием ресурса в конфигурации его необходимо импортировать с помощью командлета [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="d2611-126">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="d2611-127">Конфигурации могут содержать несколько экземпляров одного типа ресурса.</span><span class="sxs-lookup"><span data-stu-id="d2611-127">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="d2611-128">Имя каждого экземпляра должно быть уникально.</span><span class="sxs-lookup"><span data-stu-id="d2611-128">Each instance must be uniquely named.</span></span> <span data-ttu-id="d2611-129">В следующем примере второй блок ресурсов **Служба** добавляется для настройки службы DHCP.</span><span class="sxs-lookup"><span data-stu-id="d2611-129">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="d2611-130">Начиная с PowerShell 5.0, технология IntelliSense включена в DSC.</span><span class="sxs-lookup"><span data-stu-id="d2611-130">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="d2611-131">Новая функция позволяет использовать клавиши <kbd>TAB</kbd> и <kbd>CTRL</kbd>+<kbd>ПРОБЕЛ</kbd> для автозаполнения имен ключей.</span><span class="sxs-lookup"><span data-stu-id="d2611-131">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Технология IntelliSense с использованием заполнения нажатием клавиши TAB](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="d2611-133">Типы ресурсов</span><span class="sxs-lookup"><span data-stu-id="d2611-133">Types of resources</span></span>

<span data-ttu-id="d2611-134">В Windows имеются встроенные ресурсы. Кроме того, существуют ресурсы для ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="d2611-134">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="d2611-135">Имеются ресурсы для [межузловых зависимостей](../configurations/crossNodeDependencies.md), ресурсы для управления пакетами, а также [ресурсы, принадлежащие сообществу и поддерживаемые им](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="d2611-135">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="d2611-136">Шаги, описанные выше, можно использовать для определения синтаксиса этих ресурсов и способов их использования.</span><span class="sxs-lookup"><span data-stu-id="d2611-136">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="d2611-137">Страницы, на которых было описано использование этих ресурсов, собраны в разделе **Справочные материалы**.</span><span class="sxs-lookup"><span data-stu-id="d2611-137">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="d2611-138">Встроенные ресурсы Windows</span><span class="sxs-lookup"><span data-stu-id="d2611-138">Windows built-in resources</span></span>

- [<span data-ttu-id="d2611-139">Ресурс Archive</span><span class="sxs-lookup"><span data-stu-id="d2611-139">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="d2611-140">Ресурс Environment</span><span class="sxs-lookup"><span data-stu-id="d2611-140">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="d2611-141">Ресурс File</span><span class="sxs-lookup"><span data-stu-id="d2611-141">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="d2611-142">Ресурс Group</span><span class="sxs-lookup"><span data-stu-id="d2611-142">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="d2611-143">Ресурс GroupSet</span><span class="sxs-lookup"><span data-stu-id="d2611-143">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="d2611-144">Ресурс Log</span><span class="sxs-lookup"><span data-stu-id="d2611-144">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="d2611-145">Ресурс Package</span><span class="sxs-lookup"><span data-stu-id="d2611-145">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="d2611-146">Ресурс ProcessSet</span><span class="sxs-lookup"><span data-stu-id="d2611-146">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="d2611-147">Ресурс Registry</span><span class="sxs-lookup"><span data-stu-id="d2611-147">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="d2611-148">Ресурс Script</span><span class="sxs-lookup"><span data-stu-id="d2611-148">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="d2611-149">Ресурс Service</span><span class="sxs-lookup"><span data-stu-id="d2611-149">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="d2611-150">Ресурс ServiceSet</span><span class="sxs-lookup"><span data-stu-id="d2611-150">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="d2611-151">Ресурс User</span><span class="sxs-lookup"><span data-stu-id="d2611-151">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="d2611-152">Ресурс WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="d2611-152">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="d2611-153">Ресурс WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d2611-153">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="d2611-154">Ресурс WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="d2611-154">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="d2611-155">Ресурс WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d2611-155">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="d2611-156">Ресурс WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="d2611-156">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="d2611-157">Ресурс WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="d2611-157">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="d2611-158">Ресурсы межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="d2611-158">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="d2611-159">Ресурс WaitForAll</span><span class="sxs-lookup"><span data-stu-id="d2611-159">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="d2611-160">Ресурс WaitForSome</span><span class="sxs-lookup"><span data-stu-id="d2611-160">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="d2611-161">Ресурс WaitForAny</span><span class="sxs-lookup"><span data-stu-id="d2611-161">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="d2611-162">Ресурсы управления пакетами</span><span class="sxs-lookup"><span data-stu-id="d2611-162">Package Management resources</span></span>

- [<span data-ttu-id="d2611-163">Ресурс PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d2611-163">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="d2611-164">Ресурс PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="d2611-164">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="d2611-165">Ресурсы Linux</span><span class="sxs-lookup"><span data-stu-id="d2611-165">Linux resources</span></span>

- [<span data-ttu-id="d2611-166">Ресурс Linux Archive</span><span class="sxs-lookup"><span data-stu-id="d2611-166">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- <span data-ttu-id="d2611-167">Ресурс [Linux Environment](../reference/resources/linux/lnxEnvironmentResource.md)</span><span class="sxs-lookup"><span data-stu-id="d2611-167">[Linux Environment Resource](../reference/resources/linux/lnxEnvironmentResource.md)</span></span>
- [<span data-ttu-id="d2611-168">Ресурс Linux FileLine</span><span class="sxs-lookup"><span data-stu-id="d2611-168">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="d2611-169">Ресурс Linux File</span><span class="sxs-lookup"><span data-stu-id="d2611-169">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="d2611-170">Ресурс Linux Group</span><span class="sxs-lookup"><span data-stu-id="d2611-170">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="d2611-171">Ресурс Linux Package</span><span class="sxs-lookup"><span data-stu-id="d2611-171">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="d2611-172">Ресурс Linux Script</span><span class="sxs-lookup"><span data-stu-id="d2611-172">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="d2611-173">Ресурс Linux Service</span><span class="sxs-lookup"><span data-stu-id="d2611-173">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="d2611-174">Ресурс Linux SshAuthorizedKeys</span><span class="sxs-lookup"><span data-stu-id="d2611-174">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="d2611-175">Ресурс Linux User</span><span class="sxs-lookup"><span data-stu-id="d2611-175">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
