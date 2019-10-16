---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
ms.openlocfilehash: 1f77b5e6630a2e3de6e1d1a05638f94d2df039ae
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954251"
---
# <a name="dsc-resources"></a><span data-ttu-id="61cee-103">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="61cee-103">DSC Resources</span></span>

><span data-ttu-id="61cee-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="61cee-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="61cee-105">Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="61cee-105">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="61cee-106">В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).</span><span class="sxs-lookup"><span data-stu-id="61cee-106">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="61cee-107">Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="61cee-107">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span>  <span data-ttu-id="61cee-108">Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="61cee-108">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="61cee-109">Каждый ресурс содержит \*схему, которая определяет синтаксис, используемый ресурсом при [конфигурации](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="61cee-109">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="61cee-110">Схема ресурса может быть определена следующими способами.</span><span class="sxs-lookup"><span data-stu-id="61cee-110">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="61cee-111">Файлом **Schema.Mof**. Большинство ресурсов определяют свою *схему* в файле schema.mof с помощью [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="61cee-111">**'Schema.Mof'** file: Most resources define their *schema* in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="61cee-112">Файлом **\<Имя ресурса\>.schema.psm1**. [Составные ресурсы](../configurations/compositeConfigs.md) определяют свою *схему* в файле <ResourceName>.schema.psm1 с помощью [блока параметров](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="61cee-112">**'\<Resource Name\>.schema.psm1'** file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a '<ResourceName>.schema.psm1' file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="61cee-113">Файлом **\<Имя ресурса\>.psm1**. Ресурсы DSC, основанные на классе, определяют свою *схему* в описании класса.</span><span class="sxs-lookup"><span data-stu-id="61cee-113">**'\<Resource Name\>.psm1'** file: Class based DSC resources define their *schema* in the class definition.</span></span> <span data-ttu-id="61cee-114">Элементы синтаксиса обозначаются как свойства класса.</span><span class="sxs-lookup"><span data-stu-id="61cee-114">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="61cee-115">Дополнительные сведения см. в статье [About Classes and Desired State Configuration](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc) (О классах и настройке требуемого состояния).</span><span class="sxs-lookup"><span data-stu-id="61cee-115">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="61cee-116">Чтобы получить синтаксис из ресурса DSC, используйте командлет [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) вместе с параметром `-Syntax`.</span><span class="sxs-lookup"><span data-stu-id="61cee-116">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="61cee-117">Это похоже на использование командлета [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с параметром `-Syntax` для получения синтаксиса командлета.</span><span class="sxs-lookup"><span data-stu-id="61cee-117">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="61cee-118">В выходных данных будет показан шаблон, используемый в указанном блоке ресурса.</span><span class="sxs-lookup"><span data-stu-id="61cee-118">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="61cee-119">Выходные данные должны соответствовать выходным данным, приведенным ниже, так как в будущем этот ресурс может измениться.</span><span class="sxs-lookup"><span data-stu-id="61cee-119">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="61cee-120">Например, синтаксис командлета, для которого *ключи* в квадратных скобках являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="61cee-120">Like cmdlet syntax, the *keys* seen in square brackets, are optional.</span></span> <span data-ttu-id="61cee-121">Типы указывают типы данных для каждого ключа в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="61cee-121">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="61cee-122">Ключ **Ensure** является необязательным, так как Present является его значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cee-122">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

<span data-ttu-id="61cee-123">Блок ресурсов **Служба** внутри конфигурации может выглядеть следующим образом. Это необходимо, чтобы **убедиться**, что служба подсистемы печати работает.</span><span class="sxs-lookup"><span data-stu-id="61cee-123">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="61cee-124">Перед использованием ресурса в конфигурации его необходимо импортировать с помощью командлета [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="61cee-124">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="61cee-125">Конфигурации могут содержать несколько экземпляров одного типа ресурса.</span><span class="sxs-lookup"><span data-stu-id="61cee-125">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="61cee-126">Имя каждого экземпляра должно быть уникально.</span><span class="sxs-lookup"><span data-stu-id="61cee-126">Each instance must be uniquely named.</span></span> <span data-ttu-id="61cee-127">В следующем примере второй блок ресурсов **Служба** добавляется для настройки службы DHCP.</span><span class="sxs-lookup"><span data-stu-id="61cee-127">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="61cee-128">Начиная с PowerShell 5.0, Intellisense была включена в DSC.</span><span class="sxs-lookup"><span data-stu-id="61cee-128">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="61cee-129">Новая функция позволяет использовать клавиши \<TAB\> и \<CTRL+Space\> для автозаполнения имен ключей.</span><span class="sxs-lookup"><span data-stu-id="61cee-129">This new feature allows you to use \<TAB\> and \<Ctrl+Space\> to auto-complete key names.</span></span>

![Нажатие клавиши TAB для заполнения ресурса](../media/resource-tabcompletion.png)

## <a name="built-in-resources"></a><span data-ttu-id="61cee-131">Встроенные ресурсы</span><span class="sxs-lookup"><span data-stu-id="61cee-131">Built-in resources</span></span>

<span data-ttu-id="61cee-132">В дополнение к ресурсам сообщества существуют ресурсы, встроенные в Windows, ресурсы для Linux, а также ресурсы для межузловых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="61cee-132">In addition to community resources, there are built-in resources for Windows, resources for Linux, and resources for cross-node dependency.</span></span> <span data-ttu-id="61cee-133">Шаги, описанные выше, можно использовать для определения синтаксиса этих ресурсов и способов их использования.</span><span class="sxs-lookup"><span data-stu-id="61cee-133">You can use the steps above to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="61cee-134">Страницы, на которых было описано использование этих ресурсов, собраны в разделе **Справочные материалы**.</span><span class="sxs-lookup"><span data-stu-id="61cee-134">The pages that serve these resources have been archived under **Reference**.</span></span>

<span data-ttu-id="61cee-135">Встроенные ресурсы Windows</span><span class="sxs-lookup"><span data-stu-id="61cee-135">Windows built-in resources</span></span>

* [<span data-ttu-id="61cee-136">Ресурс Archive</span><span class="sxs-lookup"><span data-stu-id="61cee-136">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
* [<span data-ttu-id="61cee-137">Ресурс Environment</span><span class="sxs-lookup"><span data-stu-id="61cee-137">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
* [<span data-ttu-id="61cee-138">Ресурс File</span><span class="sxs-lookup"><span data-stu-id="61cee-138">File Resource</span></span>](../reference/resources/windows/fileResource.md)
* [<span data-ttu-id="61cee-139">Ресурс Group</span><span class="sxs-lookup"><span data-stu-id="61cee-139">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
* [<span data-ttu-id="61cee-140">Ресурс GroupSet</span><span class="sxs-lookup"><span data-stu-id="61cee-140">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
* [<span data-ttu-id="61cee-141">Ресурс Log</span><span class="sxs-lookup"><span data-stu-id="61cee-141">Log Resource</span></span>](../reference/resources/windows/logResource.md)
* [<span data-ttu-id="61cee-142">Ресурс Package</span><span class="sxs-lookup"><span data-stu-id="61cee-142">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
* [<span data-ttu-id="61cee-143">Ресурс ProcessSet</span><span class="sxs-lookup"><span data-stu-id="61cee-143">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
* [<span data-ttu-id="61cee-144">Ресурс Registry</span><span class="sxs-lookup"><span data-stu-id="61cee-144">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
* [<span data-ttu-id="61cee-145">Ресурс Script</span><span class="sxs-lookup"><span data-stu-id="61cee-145">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
* [<span data-ttu-id="61cee-146">Ресурс Service</span><span class="sxs-lookup"><span data-stu-id="61cee-146">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
* [<span data-ttu-id="61cee-147">Ресурс ServiceSet</span><span class="sxs-lookup"><span data-stu-id="61cee-147">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
* [<span data-ttu-id="61cee-148">Ресурс User</span><span class="sxs-lookup"><span data-stu-id="61cee-148">User Resource</span></span>](../reference/resources/windows/userResource.md)
* [<span data-ttu-id="61cee-149">Ресурс WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="61cee-149">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
* [<span data-ttu-id="61cee-150">Ресурс WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="61cee-150">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
* [<span data-ttu-id="61cee-151">Ресурс WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="61cee-151">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
* [<span data-ttu-id="61cee-152">Ресурс WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="61cee-152">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
* [<span data-ttu-id="61cee-153">Ресурс WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="61cee-153">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
* [<span data-ttu-id="61cee-154">Ресурс WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="61cee-154">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

<span data-ttu-id="61cee-155">Ресурсы [межузловых зависимостей](../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="61cee-155">[Cross-Node dependency](../configurations/crossNodeDependencies.md) resources</span></span>

* [<span data-ttu-id="61cee-156">Ресурс WaitForAll</span><span class="sxs-lookup"><span data-stu-id="61cee-156">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
* [<span data-ttu-id="61cee-157">Ресурс WaitForSome</span><span class="sxs-lookup"><span data-stu-id="61cee-157">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
* [<span data-ttu-id="61cee-158">Ресурс WaitForAny</span><span class="sxs-lookup"><span data-stu-id="61cee-158">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

<span data-ttu-id="61cee-159">Ресурсы управления пакетами</span><span class="sxs-lookup"><span data-stu-id="61cee-159">Package Management resources</span></span>

* [<span data-ttu-id="61cee-160">Ресурс PackageManagement</span><span class="sxs-lookup"><span data-stu-id="61cee-160">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
* [<span data-ttu-id="61cee-161">Ресурс PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="61cee-161">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

<span data-ttu-id="61cee-162">Ресурсы Linux</span><span class="sxs-lookup"><span data-stu-id="61cee-162">Linux resources</span></span>

* [<span data-ttu-id="61cee-163">Ресурс Linux Archive</span><span class="sxs-lookup"><span data-stu-id="61cee-163">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
* <span data-ttu-id="61cee-164">Ресурс [Linux Environment](../reference/resources/linux/lnxEnvironmentResource.md)</span><span class="sxs-lookup"><span data-stu-id="61cee-164">[Linux Environment Resource](../reference/resources/linux/lnxEnvironmentResource.md)</span></span>
* [<span data-ttu-id="61cee-165">Ресурс Linux FileLine</span><span class="sxs-lookup"><span data-stu-id="61cee-165">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
* [<span data-ttu-id="61cee-166">Ресурс Linux File</span><span class="sxs-lookup"><span data-stu-id="61cee-166">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
* [<span data-ttu-id="61cee-167">Ресурс Linux Group</span><span class="sxs-lookup"><span data-stu-id="61cee-167">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
* [<span data-ttu-id="61cee-168">Ресурс Linux Package</span><span class="sxs-lookup"><span data-stu-id="61cee-168">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
* [<span data-ttu-id="61cee-169">Ресурс Linux Script</span><span class="sxs-lookup"><span data-stu-id="61cee-169">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
* [<span data-ttu-id="61cee-170">Ресурс Linux Service</span><span class="sxs-lookup"><span data-stu-id="61cee-170">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
* [<span data-ttu-id="61cee-171">Ресурс Linux SshAuthorizedKeys</span><span class="sxs-lookup"><span data-stu-id="61cee-171">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
* [<span data-ttu-id="61cee-172">Ресурс Linux User</span><span class="sxs-lookup"><span data-stu-id="61cee-172">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)