---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурсы DSC
ms.openlocfilehash: 1f77b5e6630a2e3de6e1d1a05638f94d2df039ae
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54046697"
---
# <a name="dsc-resources"></a><span data-ttu-id="8677d-103">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="8677d-103">DSC Resources</span></span>

><span data-ttu-id="8677d-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8677d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="8677d-105">Ресурсы службы настройки требуемого состояния (DSC) предоставляют шаблоны для настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="8677d-105">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="8677d-106">В ресурсе представлены свойства, которые можно настроить (схема), и функции сценариев PowerShell, которые вызывает локальный диспетчер конфигураций (LCM).</span><span class="sxs-lookup"><span data-stu-id="8677d-106">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="8677d-107">Ресурс может моделировать что-либо универсальное, например файл, или конкретное, например настройку сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="8677d-107">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span>  <span data-ttu-id="8677d-108">Группы похожих ресурсов объединяются в DSC-модуль, в котором все необходимые файлы упорядочиваются в переносимую структуру и включаются метаданные для идентификации целевого предназначения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8677d-108">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="8677d-109">Каждый ресурс имеет \* схему, которая определяет синтаксис, необходимые для использования ресурса в [конфигурации](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="8677d-109">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="8677d-110">Схема ресурса, может быть определена следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8677d-110">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="8677d-111">**«Schema.Mof»** файла: Определить больше всего ресурсов их *схемы* в schema.mof файле, с использованием [формат управляющих объектов](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="8677d-111">**'Schema.Mof'** file: Most resources define their *schema* in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="8677d-112">**"\<Имя ресурса\>. schema.psm1"** файла: [Составные ресурсы](../configurations/compositeConfigs.md) определить их *схемы* в "<ResourceName>. schema.psm1" файл с помощью [блок параметров](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="8677d-112">**'\<Resource Name\>.schema.psm1'** file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a '<ResourceName>.schema.psm1' file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="8677d-113">**"\<Имя ресурса\>.psm1"** файла: Класс на основе ресурсов DSC определяют их *схемы* в определении класса.</span><span class="sxs-lookup"><span data-stu-id="8677d-113">**'\<Resource Name\>.psm1'** file: Class based DSC resources define their *schema* in the class definition.</span></span> <span data-ttu-id="8677d-114">Элементы синтаксиса, обозначаются как свойства класса.</span><span class="sxs-lookup"><span data-stu-id="8677d-114">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="8677d-115">Дополнительные сведения см. в разделе [статье "about_classes"](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span><span class="sxs-lookup"><span data-stu-id="8677d-115">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="8677d-116">Чтобы получить синтаксис для ресурсов DSC, используйте [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) командлет с `-Syntax` параметра.</span><span class="sxs-lookup"><span data-stu-id="8677d-116">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="8677d-117">Это похоже на использование [Get-Command](/powershell/module/microsoft.powershell.core/get-command) с `-Syntax` параметра, чтобы получить синтаксис командлета.</span><span class="sxs-lookup"><span data-stu-id="8677d-117">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="8677d-118">Шаблон, используемый для блока ресурсов для ресурса, указанную вами будут показаны результаты, вы увидите.</span><span class="sxs-lookup"><span data-stu-id="8677d-118">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="8677d-119">Выходные данные, которые вы видите должен соответствовать приведенному ниже, на то, что этот ресурс синтаксис может измениться в будущем.</span><span class="sxs-lookup"><span data-stu-id="8677d-119">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="8677d-120">Синтаксис командлета, такие как *ключи* видно в квадратные скобки, являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="8677d-120">Like cmdlet syntax, the *keys* seen in square brackets, are optional.</span></span> <span data-ttu-id="8677d-121">Типы укажите тип данных, которые ожидаются процессом каждого ключа.</span><span class="sxs-lookup"><span data-stu-id="8677d-121">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="8677d-122">**Убедитесь, что** ключа является необязательным, так как по умолчанию используется «Отсутствует».</span><span class="sxs-lookup"><span data-stu-id="8677d-122">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

<span data-ttu-id="8677d-123">Внутри конфигурации **службы** блоке ресурсов может выглядеть так, чтобы **убедитесь, что** , на котором работает служба диспетчера очереди печати.</span><span class="sxs-lookup"><span data-stu-id="8677d-123">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="8677d-124">Прежде чем использовать ресурс в конфигурации, необходимо импортировать его с помощью [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="8677d-124">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="8677d-125">Конфигурации может содержать несколько экземпляров одного типа ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8677d-125">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="8677d-126">Каждый экземпляр должен иметь имя уникально.</span><span class="sxs-lookup"><span data-stu-id="8677d-126">Each instance must be uniquely named.</span></span> <span data-ttu-id="8677d-127">В следующем примере второй **службы** блоке ресурсов добавляется для настройки службы «DHCP».</span><span class="sxs-lookup"><span data-stu-id="8677d-127">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="8677d-128">Начиная с PowerShell 5.0, был добавлен intellisense для DSC.</span><span class="sxs-lookup"><span data-stu-id="8677d-128">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="8677d-129">Эта новая функция позволяет использовать \<ВКЛАДКЕ\> и \<Ctrl + пробел\> для автозаполнения имен ключей.</span><span class="sxs-lookup"><span data-stu-id="8677d-129">This new feature allows you to use \<TAB\> and \<Ctrl+Space\> to auto-complete key names.</span></span>

![Ресурс нажатием клавиши TAB](../media/resource-tabcompletion.png)

## <a name="built-in-resources"></a><span data-ttu-id="8677d-131">Встроенные ресурсы</span><span class="sxs-lookup"><span data-stu-id="8677d-131">Built-in resources</span></span>

<span data-ttu-id="8677d-132">Помимо ресурсы сообщества существуют встроенные ресурсы для Windows, ресурсы для Linux и ресурсы для зависимостей между узлами.</span><span class="sxs-lookup"><span data-stu-id="8677d-132">In addition to community resources, there are built-in resources for Windows, resources for Linux, and resources for cross-node dependency.</span></span> <span data-ttu-id="8677d-133">Описанные выше действия можно использовать для определения синтаксис этих ресурсов и их использование.</span><span class="sxs-lookup"><span data-stu-id="8677d-133">You can use the steps above to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="8677d-134">Страницы, которые обслуживает эти ресурсы были архивированы в разделе **ссылку**.</span><span class="sxs-lookup"><span data-stu-id="8677d-134">The pages that serve these resources have been archived under **Reference**.</span></span>

<span data-ttu-id="8677d-135">Встроенные ресурсы Windows</span><span class="sxs-lookup"><span data-stu-id="8677d-135">Windows built-in resources</span></span>

* [<span data-ttu-id="8677d-136">Ресурс Archive</span><span class="sxs-lookup"><span data-stu-id="8677d-136">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
* [<span data-ttu-id="8677d-137">Ресурс Environment</span><span class="sxs-lookup"><span data-stu-id="8677d-137">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
* [<span data-ttu-id="8677d-138">Ресурс File</span><span class="sxs-lookup"><span data-stu-id="8677d-138">File Resource</span></span>](../reference/resources/windows/fileResource.md)
* [<span data-ttu-id="8677d-139">Ресурс Group</span><span class="sxs-lookup"><span data-stu-id="8677d-139">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
* [<span data-ttu-id="8677d-140">Ресурс GroupSet</span><span class="sxs-lookup"><span data-stu-id="8677d-140">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
* [<span data-ttu-id="8677d-141">Ресурс Log</span><span class="sxs-lookup"><span data-stu-id="8677d-141">Log Resource</span></span>](../reference/resources/windows/logResource.md)
* [<span data-ttu-id="8677d-142">Ресурс Package</span><span class="sxs-lookup"><span data-stu-id="8677d-142">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
* [<span data-ttu-id="8677d-143">Ресурс ProcessSet</span><span class="sxs-lookup"><span data-stu-id="8677d-143">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
* [<span data-ttu-id="8677d-144">Ресурс Registry</span><span class="sxs-lookup"><span data-stu-id="8677d-144">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
* [<span data-ttu-id="8677d-145">Ресурс Script</span><span class="sxs-lookup"><span data-stu-id="8677d-145">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
* [<span data-ttu-id="8677d-146">Ресурс Service</span><span class="sxs-lookup"><span data-stu-id="8677d-146">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
* [<span data-ttu-id="8677d-147">Ресурс ServiceSet</span><span class="sxs-lookup"><span data-stu-id="8677d-147">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
* [<span data-ttu-id="8677d-148">Ресурс User</span><span class="sxs-lookup"><span data-stu-id="8677d-148">User Resource</span></span>](../reference/resources/windows/userResource.md)
* [<span data-ttu-id="8677d-149">Ресурс WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="8677d-149">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
* [<span data-ttu-id="8677d-150">Ресурс WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="8677d-150">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
* [<span data-ttu-id="8677d-151">Ресурс WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="8677d-151">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
* [<span data-ttu-id="8677d-152">Ресурс WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="8677d-152">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
* [<span data-ttu-id="8677d-153">WindowsPackageCabResource ресурсов</span><span class="sxs-lookup"><span data-stu-id="8677d-153">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
* [<span data-ttu-id="8677d-154">Ресурс WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="8677d-154">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

<span data-ttu-id="8677d-155">[Зависимость между узлами](../configurations/crossNodeDependencies.md) ресурсы</span><span class="sxs-lookup"><span data-stu-id="8677d-155">[Cross-Node dependency](../configurations/crossNodeDependencies.md) resources</span></span>

* [<span data-ttu-id="8677d-156">WaitForAll ресурсов</span><span class="sxs-lookup"><span data-stu-id="8677d-156">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
* [<span data-ttu-id="8677d-157">WaitForSome ресурсов</span><span class="sxs-lookup"><span data-stu-id="8677d-157">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
* [<span data-ttu-id="8677d-158">WaitForAny ресурсов</span><span class="sxs-lookup"><span data-stu-id="8677d-158">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

<span data-ttu-id="8677d-159">Ресурсы пакета управления</span><span class="sxs-lookup"><span data-stu-id="8677d-159">Package Management resources</span></span>

* [<span data-ttu-id="8677d-160">Ресурс PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8677d-160">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
* [<span data-ttu-id="8677d-161">Ресурс PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="8677d-161">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

<span data-ttu-id="8677d-162">Ресурсов под управлением Linux</span><span class="sxs-lookup"><span data-stu-id="8677d-162">Linux resources</span></span>

* [<span data-ttu-id="8677d-163">Ресурс Linux Archive</span><span class="sxs-lookup"><span data-stu-id="8677d-163">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
* [<span data-ttu-id="8677d-164">Ресурс Environment Linux</span><span class="sxs-lookup"><span data-stu-id="8677d-164">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
* [<span data-ttu-id="8677d-165">Linux FileLine ресурсов</span><span class="sxs-lookup"><span data-stu-id="8677d-165">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
* [<span data-ttu-id="8677d-166">Ресурс Linux File</span><span class="sxs-lookup"><span data-stu-id="8677d-166">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
* [<span data-ttu-id="8677d-167">Ресурс группы Linux</span><span class="sxs-lookup"><span data-stu-id="8677d-167">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
* [<span data-ttu-id="8677d-168">Ресурс Linux Package</span><span class="sxs-lookup"><span data-stu-id="8677d-168">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
* [<span data-ttu-id="8677d-169">Ресурс Script для Linux</span><span class="sxs-lookup"><span data-stu-id="8677d-169">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
* [<span data-ttu-id="8677d-170">Ресурс службы Linux</span><span class="sxs-lookup"><span data-stu-id="8677d-170">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
* [<span data-ttu-id="8677d-171">Linux SshAuthorizedKeys ресурсов</span><span class="sxs-lookup"><span data-stu-id="8677d-171">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
* [<span data-ttu-id="8677d-172">Ресурс пользователя Linux</span><span class="sxs-lookup"><span data-stu-id="8677d-172">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
