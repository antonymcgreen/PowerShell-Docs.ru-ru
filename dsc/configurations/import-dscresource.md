---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование Import-DSCResource
ms.openlocfilehash: ee0b2f0469c6507c8f0148138198597a9e57cdd7
ms.sourcegitcommit: c581c4c8036edf55147e7bce4b00c860da6c5a8b
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2019
ms.locfileid: "56803418"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="61b49-103">Использование Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="61b49-103">Using Import-DSCResource</span></span>

<span data-ttu-id="61b49-104">`Import-DScResource` — Это динамическое ключевое слово, который может использоваться только внутри блока сценария для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61b49-104">`Import-DScResource` is a dynamic keyword, which can only be used inside a Configuration script block.</span></span> <span data-ttu-id="61b49-105">`Import-DSCResource` Ключевое слово, чтобы импортировать все ресурсы, необходимые в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61b49-105">The `Import-DSCResource` keyword to import any resources needed in your Configuration.</span></span> <span data-ttu-id="61b49-106">Ресурсы в группе `$pshome` импортируются автоматически, но он по-прежнему считается наилучшим решением будет явно импортировать все ресурсы, используемые в вашей [конфигурации](Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="61b49-106">Resources under `$pshome` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="61b49-107">Синтаксис `Import-DSCResource` показан ниже.</span><span class="sxs-lookup"><span data-stu-id="61b49-107">The syntax for `Import-DSCResource` is shown below.</span></span>  <span data-ttu-id="61b49-108">При указании модули по имени, это требование, чтобы перечислить все в новой строке.</span><span class="sxs-lookup"><span data-stu-id="61b49-108">When specifying modules by name, it is a requirement to list each on a new line.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>]
```

|<span data-ttu-id="61b49-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="61b49-109">Parameter</span></span>  |<span data-ttu-id="61b49-110">Описание</span><span class="sxs-lookup"><span data-stu-id="61b49-110">Description</span></span>  |
|---------|---------|
|`-Name`|<span data-ttu-id="61b49-111">Имена ресурсов DSC, который необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="61b49-111">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="61b49-112">Если указано имя модуля, команда ищет эти ресурсы DSC в этом модуле. в противном случае команда ищет ресурсы DSC во всех путях ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="61b49-112">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="61b49-113">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="61b49-113">Wildcards are supported.</span></span>|
|`-ModuleName`|<span data-ttu-id="61b49-114">Имя модуля или спецификации модуля.</span><span class="sxs-lookup"><span data-stu-id="61b49-114">The module name, or module specification.</span></span>  <span data-ttu-id="61b49-115">Если указать ресурсы для импорта из модуля, команда будет предпринята попытка импортировать только те ресурсы.</span><span class="sxs-lookup"><span data-stu-id="61b49-115">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="61b49-116">Если указать только модуль, команда импортирует все ресурсы DSC в модуле.</span><span class="sxs-lookup"><span data-stu-id="61b49-116">If you specify the module only, the command imports all the DSC resources in the module.</span></span>|

```powershell
Import-DscResource -ModuleName xActiveDirectory;
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="61b49-117">Пример: Использование Import-DSCResource в конфигурации</span><span class="sxs-lookup"><span data-stu-id="61b49-117">Example: Use Import-DSCResource within a configuration</span></span>

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration -Name Service, File, Registry
    
    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    # As a best practice, list each requirement on a different line if possible.  This makes reviewing
    # multiple changes in source control a bit easier.
    Import-DSCResource -Name File
    Import-DSCResource -Name TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    # When specifying the modulename parameter, it is a requirement to list each on a new line.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
    Import-DSCResource -ModuleName ComputerManagementDsc
...
```

> [!NOTE]
> <span data-ttu-id="61b49-118">Указание нескольких значений для имен ресурсов и модулей в одной команде не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="61b49-118">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span> <span data-ttu-id="61b49-119">Он может иметь неопределенное поведение, о какие ресурсы для загрузки из какой модуль, если же ресурс существует в нескольких модулях.</span><span class="sxs-lookup"><span data-stu-id="61b49-119">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="61b49-120">Указанную ниже команду, приведет к ошибке во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="61b49-120">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="61b49-121">Что следует учитывать при использовании только имя параметра:</span><span class="sxs-lookup"><span data-stu-id="61b49-121">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="61b49-122">Это — ресурсоемкая операция, в зависимости от количества модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="61b49-122">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="61b49-123">Он загрузит первый ресурс с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="61b49-123">It will load the first resource found with the given name.</span></span> <span data-ttu-id="61b49-124">В случае, если существует более одного ресурса с тем же именем установлен, его удалось загрузить неправильный ресурс.</span><span class="sxs-lookup"><span data-stu-id="61b49-124">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="61b49-125">Рекомендуется использовать для указания `–ModuleName` с `-Name` параметра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="61b49-125">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="61b49-126">Такое использование имеет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="61b49-126">This usage has the following benefits:</span></span>

- <span data-ttu-id="61b49-127">Он уменьшает влияние на производительность, ограничивая область поиска для указанного ресурса.</span><span class="sxs-lookup"><span data-stu-id="61b49-127">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="61b49-128">Он явно определяет модуль определения ресурса, убедитесь, что загружается необходимого ресурса.</span><span class="sxs-lookup"><span data-stu-id="61b49-128">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="61b49-129">В PowerShell 5.0 ресурсы DSC могут иметь несколько версий, и эти версии можно устанавливать на компьютере параллельно.</span><span class="sxs-lookup"><span data-stu-id="61b49-129">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="61b49-130">Это реализуется благодаря наличию нескольких версий модуля ресурсов, которые содержатся в одной папке модуля.</span><span class="sxs-lookup"><span data-stu-id="61b49-130">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span>
> <span data-ttu-id="61b49-131">Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="61b49-131">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="61b49-132">IntelliSense с Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="61b49-132">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="61b49-133">При создании конфигурации DSC в интегрированной среде Сценариев, PowerShell предоставляет IntelliSence для ресурсов и их свойств.</span><span class="sxs-lookup"><span data-stu-id="61b49-133">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="61b49-134">Определения ресурсов в группе `$pshome` путь к модулю загружаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="61b49-134">Resource definitions under the `$pshome` module path are loaded automatically.</span></span> <span data-ttu-id="61b49-135">При импорте ресурсов с помощью `Import-DSCResource` ключевое слово, добавляются определения указанного ресурса и Intellisense расширяется для включения схемы импортируемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="61b49-135">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![Intellisense ресурсов](/media/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="61b49-137">Начиная с PowerShell 5.0, был добавлен нажатием клавиши TAB в интегрированную среду сценариев для ресурсов DSC и их свойства.</span><span class="sxs-lookup"><span data-stu-id="61b49-137">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="61b49-138">Дополнительные сведения см. в разделе [ресурсы](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="61b49-138">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="61b49-139">При компиляции конфигурации, PowerShell использует определения импортируемого ресурса для проверки всех блоков ресурсов в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61b49-139">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span>
<span data-ttu-id="61b49-140">Проверяется каждый блок ресурсов, с помощью определения схемы ресурса, для следующих правил.</span><span class="sxs-lookup"><span data-stu-id="61b49-140">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="61b49-141">Используются только свойства, определенные в схеме.</span><span class="sxs-lookup"><span data-stu-id="61b49-141">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="61b49-142">Типы данных для каждого свойства заданы правильно.</span><span class="sxs-lookup"><span data-stu-id="61b49-142">The data types for each property are correct.</span></span>
- <span data-ttu-id="61b49-143">Указаны свойства ключей.</span><span class="sxs-lookup"><span data-stu-id="61b49-143">Keys properties are specified.</span></span>
- <span data-ttu-id="61b49-144">Используется не свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="61b49-144">No read-only property is used.</span></span>
- <span data-ttu-id="61b49-145">Проверки на значение сопоставляет типы.</span><span class="sxs-lookup"><span data-stu-id="61b49-145">Validation on value maps types.</span></span>

<span data-ttu-id="61b49-146">Рассмотрим следующую конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="61b49-146">Consider the following configuration:</span></span>

```powershell
Configuration SchemaValidationInCorrectEnumValue
{
    # It is best practice to explicitly import all resources used in your Configuration.
    # This includes resources that are imported automatically, like WindowsFeature.
    Import-DSCResource -Name WindowsFeature
    Node localhost
    {
        WindowsFeature ROLE1
        {
            Name = “Telnet-Client”
            Ensure = “Invalid”
        }
    }
}
```

<span data-ttu-id="61b49-147">Компиляция этой конфигурации приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="61b49-147">Compiling this Configuration results in an error.</span></span>

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values ‘Invalid’ is not supported or valid for property ‘Ensure’ on class ‘WindowsFeature’. Please specify only supported values: Present, Absent.
```

<span data-ttu-id="61b49-148">IntelliSense и схемы проверки можно перехватить больше ошибок во время синтаксического анализа и компиляции, как избежать сложностей во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="61b49-148">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="61b49-149">Каждый ресурс DSC может иметь имя и **FriendlyName** определением схемы ресурса.</span><span class="sxs-lookup"><span data-stu-id="61b49-149">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="61b49-150">Ниже приведены две первые строки «MSFT_ServiceResource.shema.mof».</span><span class="sxs-lookup"><span data-stu-id="61b49-150">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> <span data-ttu-id="61b49-151">При использовании этого ресурса в конфигурации, можно указать **MSFT_ServiceResource** или **службы**.</span><span class="sxs-lookup"><span data-stu-id="61b49-151">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="61b49-152">PowerShell v4 и v5 различия</span><span class="sxs-lookup"><span data-stu-id="61b49-152">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="61b49-153">Существует несколько различий, получаемых при создании конфигурации в PowerShell 4.0 Visual Studio. PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="61b49-153">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="61b49-154">В этом разделе будут указаны различия, отображается отношение к этой статье.</span><span class="sxs-lookup"><span data-stu-id="61b49-154">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="61b49-155">Несколько версий ресурсов</span><span class="sxs-lookup"><span data-stu-id="61b49-155">Multiple Resource Versions</span></span>

<span data-ttu-id="61b49-156">Установка и использование нескольких версий ресурсы параллельно не поддерживается в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="61b49-156">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="61b49-157">Если вы заметили проблемы при импорте ресурсов в вашей конфигурации, убедитесь, что имеется только одна версия установки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="61b49-157">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="61b49-158">На рисунке ниже, две версии **xPSDesiredStateConfiguration** устанавливаются модуля.</span><span class="sxs-lookup"><span data-stu-id="61b49-158">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![Несколько версий ресурсов исправлена](/media/multiple-resource-versions-broken.md)

<span data-ttu-id="61b49-160">Скопируйте содержимое версии нужный модуль на верхний уровень каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="61b49-160">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![Несколько версий ресурсов исправлена](/media/multiple-resource-versions-fixed.md)

### <a name="resource-location"></a><span data-ttu-id="61b49-162">Расположение ресурса</span><span class="sxs-lookup"><span data-stu-id="61b49-162">Resource location</span></span>

<span data-ttu-id="61b49-163">При разработке и компилирование конфигураций, ресурсы могут храниться в любой каталог, указанный в вашей [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path).</span><span class="sxs-lookup"><span data-stu-id="61b49-163">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path).</span></span> <span data-ttu-id="61b49-164">В PowerShell 4.0, LCM требуются все модули ресурсов DSC для сохранения в разделе «Программы Files\WindowsPowerShell\Modules» или `$pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="61b49-164">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="61b49-165">Начиная с PowerShell 5.0, и это требование было удалено, а модули ресурсов, которые могут храниться в любой каталог, заданный параметром `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="61b49-165">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

## <a name="see-also"></a><span data-ttu-id="61b49-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="61b49-166">See also</span></span>

- [<span data-ttu-id="61b49-167">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="61b49-167">Resources</span></span>](../resources/resources.md)
