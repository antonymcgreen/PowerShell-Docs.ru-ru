---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование Import-DSCResource
ms.openlocfilehash: e1c2c06d756a70c2de516f330e3123235ce740ba
ms.sourcegitcommit: 02eed65c526ef19cf952c2129f280bb5615bf0c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70215405"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="24f30-103">Использование Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="24f30-103">Using Import-DSCResource</span></span>

<span data-ttu-id="24f30-104">`Import-DScResource` — это динамическое ключевое слово, которое может использоваться только внутри блока сценария конфигурации.</span><span class="sxs-lookup"><span data-stu-id="24f30-104">`Import-DScResource` is a dynamic keyword, which can only be used inside a Configuration script block.</span></span> <span data-ttu-id="24f30-105">Ключевое слово `Import-DSCResource` используется для импорта всех ресурсов, необходимых в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="24f30-105">The `Import-DSCResource` keyword to import any resources needed in your Configuration.</span></span> <span data-ttu-id="24f30-106">Ресурсы в `$pshome` импортируются автоматически, но по-прежнему рекомендуется явным образом импортировать все ресурсы, используемые в [конфигурации](Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="24f30-106">Resources under `$pshome` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="24f30-107">Ниже показан синтаксис для ключевого слова `Import-DSCResource`.</span><span class="sxs-lookup"><span data-stu-id="24f30-107">The syntax for `Import-DSCResource` is shown below.</span></span>  <span data-ttu-id="24f30-108">При указании модулей по имени необходимо перечислять каждый модуль в новой строке.</span><span class="sxs-lookup"><span data-stu-id="24f30-108">When specifying modules by name, it is a requirement to list each on a new line.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>]
```

|<span data-ttu-id="24f30-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="24f30-109">Parameter</span></span>  |<span data-ttu-id="24f30-110">Описание</span><span class="sxs-lookup"><span data-stu-id="24f30-110">Description</span></span>  |
|---------|---------|
|`-Name`|<span data-ttu-id="24f30-111">Имена ресурсов DSC, которые необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="24f30-111">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="24f30-112">Если указано имя модуля, команда ищет эти ресурсы DSC в этом модуле. В противном случае команда ищет ресурсы DSC во всех путях ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="24f30-112">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="24f30-113">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="24f30-113">Wildcards are supported.</span></span>|
|`-ModuleName`|<span data-ttu-id="24f30-114">Имя или спецификация модуля.</span><span class="sxs-lookup"><span data-stu-id="24f30-114">The module name, or module specification.</span></span>  <span data-ttu-id="24f30-115">Если указать ресурсы для импорта из модуля, команда предпримет попытку импортировать только эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="24f30-115">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="24f30-116">Если указать только модуль, команда импортирует все ресурсы DSC в модуле.</span><span class="sxs-lookup"><span data-stu-id="24f30-116">If you specify the module only, the command imports all the DSC resources in the module.</span></span>|

```powershell
Import-DscResource -ModuleName xActiveDirectory;
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="24f30-117">Пример: использование Import-DSCResource в конфигурации</span><span class="sxs-lookup"><span data-stu-id="24f30-117">Example: Use Import-DSCResource within a configuration</span></span>

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
> <span data-ttu-id="24f30-118">Указание нескольких значений для имен ресурсов и модулей в одной команде не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="24f30-118">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span> <span data-ttu-id="24f30-119">Это может привести к недетерминированному поведению относительно того, с какого ресурса необходимо загружать тот или иной модуль, в случае если один и тот же ресурс существует в нескольких модулях.</span><span class="sxs-lookup"><span data-stu-id="24f30-119">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="24f30-120">Приведенная ниже команда вызовет ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="24f30-120">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="24f30-121">Аспекты, которые следует учитывать при использовании только параметра имени:</span><span class="sxs-lookup"><span data-stu-id="24f30-121">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="24f30-122">Это может быть ресурсоемкая операция в зависимости от количества установленных на компьютере модулей.</span><span class="sxs-lookup"><span data-stu-id="24f30-122">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="24f30-123">Она загрузит первый найденный ресурс с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="24f30-123">It will load the first resource found with the given name.</span></span> <span data-ttu-id="24f30-124">В случае если существует несколько ресурсов с одним именем, она может загрузить не тот ресурс.</span><span class="sxs-lookup"><span data-stu-id="24f30-124">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="24f30-125">Рекомендуется указать `–ModuleName` с параметром `-Name`, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="24f30-125">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="24f30-126">Это обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="24f30-126">This usage has the following benefits:</span></span>

- <span data-ttu-id="24f30-127">Уменьшается влияние на производительность за счет ограничения области поиска для указанного ресурса.</span><span class="sxs-lookup"><span data-stu-id="24f30-127">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="24f30-128">В этом случае явно задается определяющий ресурс модуль, обеспечивая загрузку нужного ресурса.</span><span class="sxs-lookup"><span data-stu-id="24f30-128">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="24f30-129">В PowerShell 5.0 ресурсы DSC могут иметь несколько версий, и эти версии можно устанавливать на компьютере параллельно.</span><span class="sxs-lookup"><span data-stu-id="24f30-129">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="24f30-130">Это реализуется благодаря наличию нескольких версий модуля ресурсов, которые содержатся в одной папке модуля.</span><span class="sxs-lookup"><span data-stu-id="24f30-130">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span>
> <span data-ttu-id="24f30-131">Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="24f30-131">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="24f30-132">Технология IntelliSense с Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="24f30-132">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="24f30-133">При создании конфигурации DSC в ISE программа PowerShell предоставляет IntelliSence для ресурсов и их свойств.</span><span class="sxs-lookup"><span data-stu-id="24f30-133">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="24f30-134">Определения ресурсов в пути модуля `$pshome` загружаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="24f30-134">Resource definitions under the `$pshome` module path are loaded automatically.</span></span> <span data-ttu-id="24f30-135">При импорте ресурсов с использованием ключевого слова `Import-DSCResource` добавляются определения указанного ресурса и в Intellisense добавляется схема импортируемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="24f30-135">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![Применение технологии Intellisense для ресурса](../media/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="24f30-137">Начиная с PowerShell 5.0 в ISE было добавлено завершение нажатием клавиши TAB для ресурсов DSC и их свойств.</span><span class="sxs-lookup"><span data-stu-id="24f30-137">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="24f30-138">Дополнительные сведения см. в статье о [ресурсах DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="24f30-138">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="24f30-139">При компиляции конфигурации PowerShell использует импортированные определения ресурсов, чтобы проверить все блоки ресурсов в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="24f30-139">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span>
<span data-ttu-id="24f30-140">Каждый блок ресурсов проверяется с использованием определения схемы ресурса на соответствие следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="24f30-140">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="24f30-141">используются только свойства, определенные в схеме;</span><span class="sxs-lookup"><span data-stu-id="24f30-141">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="24f30-142">типы данных для каждого свойства заданы правильно;</span><span class="sxs-lookup"><span data-stu-id="24f30-142">The data types for each property are correct.</span></span>
- <span data-ttu-id="24f30-143">свойства ключей заданы;</span><span class="sxs-lookup"><span data-stu-id="24f30-143">Keys properties are specified.</span></span>
- <span data-ttu-id="24f30-144">свойство только для чтения не используется;</span><span class="sxs-lookup"><span data-stu-id="24f30-144">No read-only property is used.</span></span>
- <span data-ttu-id="24f30-145">проверка типов сопоставлений значения.</span><span class="sxs-lookup"><span data-stu-id="24f30-145">Validation on value maps types.</span></span>

<span data-ttu-id="24f30-146">Рассмотрим следующую конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="24f30-146">Consider the following configuration:</span></span>

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

<span data-ttu-id="24f30-147">Компиляция этой конфигурации приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="24f30-147">Compiling this Configuration results in an error.</span></span>

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values ‘Invalid’ is not supported or valid for property ‘Ensure’ on class ‘WindowsFeature’. Please specify only supported values: Present, Absent.
```

<span data-ttu-id="24f30-148">IntelliSense и проверка схемы позволяют обнаруживать больше ошибок во время анализа и компиляции, избегая осложнений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="24f30-148">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="24f30-149">Каждый ресурс DSC может иметь имя и **FriendlyName**, определенное схемой ресурса.</span><span class="sxs-lookup"><span data-stu-id="24f30-149">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="24f30-150">Ниже приведены две первые строки файла MSFT_ServiceResource.shema.mof.</span><span class="sxs-lookup"><span data-stu-id="24f30-150">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> <span data-ttu-id="24f30-151">При использовании этого ресурса в конфигурации можно указать **MSFT_ServiceResource** или **Service**.</span><span class="sxs-lookup"><span data-stu-id="24f30-151">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="24f30-152">Различия PowerShell версий 4 и 5</span><span class="sxs-lookup"><span data-stu-id="24f30-152">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="24f30-153">Существует несколько различий, заметных при создании конфигураций в PowerShell версии 4.0, 5.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="24f30-153">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="24f30-154">В этом разделе освещены различия, которые имеют отношение к этой статье.</span><span class="sxs-lookup"><span data-stu-id="24f30-154">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="24f30-155">Несколько версий ресурсов</span><span class="sxs-lookup"><span data-stu-id="24f30-155">Multiple Resource Versions</span></span>

<span data-ttu-id="24f30-156">Установка нескольких версий ресурсов и их параллельное использование не поддерживаются в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="24f30-156">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="24f30-157">Если вы заметили проблемы при импорте ресурсов в свою конфигурацию, убедитесь, что установлена только одна версия ресурса.</span><span class="sxs-lookup"><span data-stu-id="24f30-157">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="24f30-158">На рисунке ниже показано, что установлены две версии модуля **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="24f30-158">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![Исправление нескольких версий ресурсов](../media/multiple-resource-versions-broken.png)

<span data-ttu-id="24f30-160">Скопируйте содержимое нужной версии модуля на верхний уровень каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="24f30-160">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![Исправление нескольких версий ресурсов](../media/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a><span data-ttu-id="24f30-162">Расположение ресурса</span><span class="sxs-lookup"><span data-stu-id="24f30-162">Resource location</span></span>

<span data-ttu-id="24f30-163">При разработке и компилировании конфигураций ваши ресурсы можно хранить в любом каталоге, указанном в параметре [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path).</span><span class="sxs-lookup"><span data-stu-id="24f30-163">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path).</span></span> <span data-ttu-id="24f30-164">В PowerShell 4.0 диспетчер LCM требовал, чтобы все модули ресурсов DSC хранились по пути Program Files\WindowsPowerShell\Modules или `$pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="24f30-164">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="24f30-165">Начиная с PowerShell 5.0 это требование было удалено, а модули ресурсов могут храниться в любом каталоге, заданном с помощью параметра `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="24f30-165">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

## <a name="see-also"></a><span data-ttu-id="24f30-166">См. также статью</span><span class="sxs-lookup"><span data-stu-id="24f30-166">See also</span></span>

- [<span data-ttu-id="24f30-167">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="24f30-167">Resources</span></span>](../resources/resources.md)
