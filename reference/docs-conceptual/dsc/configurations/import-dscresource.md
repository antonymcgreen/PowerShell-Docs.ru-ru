---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Использование Import-DSCResource
description: Import-DSCResource — это динамическое ключевое слово, которое можно использовать только внутри блока скрипта конфигурации. Оно используется для импорта модулей ресурса, необходимых для конфигурации.
ms.openlocfilehash: f6dcad2c56848ec25eb79332c96fe6b0d438fe95
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658514"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="30f86-105">Использование Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="30f86-105">Using Import-DSCResource</span></span>

<span data-ttu-id="30f86-106">`Import-DSCResource` — это динамическое ключевое слово, которое можно использовать только в блоке скрипта конфигурации для импорта любых ресурсов, необходимых для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="30f86-106">`Import-DSCResource` is a dynamic keyword, which can only be used inside a Configuration script block to import any resources needed in your Configuration.</span></span> <span data-ttu-id="30f86-107">Ресурсы в `$PSHOME` импортируются автоматически, но по-прежнему рекомендуется явным образом импортировать все ресурсы, используемые в [конфигурации](Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="30f86-107">Resources under `$PSHOME` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="30f86-108">Ниже показан синтаксис для ключевого слова `Import-DSCResource`.</span><span class="sxs-lookup"><span data-stu-id="30f86-108">The syntax for `Import-DSCResource` is shown below.</span></span> <span data-ttu-id="30f86-109">При указании модулей по имени необходимо перечислять каждый модуль в новой строке.</span><span class="sxs-lookup"><span data-stu-id="30f86-109">When specifying modules by name, it is a requirement to list each on a new line.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>] [-ModuleVersion <ModuleVersion>]
```

|    <span data-ttu-id="30f86-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="30f86-110">Parameter</span></span>     |                                                                                                                      <span data-ttu-id="30f86-111">Описание</span><span class="sxs-lookup"><span data-stu-id="30f86-111">Description</span></span>                                                                                                                      |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-Name`          | <span data-ttu-id="30f86-112">Имена ресурсов DSC, которые необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="30f86-112">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="30f86-113">Если указано имя модуля, команда ищет эти ресурсы DSC в этом модуле. В противном случае команда ищет ресурсы DSC во всех путях ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="30f86-113">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="30f86-114">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="30f86-114">Wildcards are supported.</span></span> |
| `-ModuleName`    | <span data-ttu-id="30f86-115">Имя или спецификация модуля.</span><span class="sxs-lookup"><span data-stu-id="30f86-115">The module name, or module specification.</span></span>  <span data-ttu-id="30f86-116">Если указать ресурсы для импорта из модуля, команда предпримет попытку импортировать только эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="30f86-116">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="30f86-117">Если указать только модуль, команда импортирует все ресурсы DSC в модуле.</span><span class="sxs-lookup"><span data-stu-id="30f86-117">If you specify the module only, the command imports all the DSC resources in the module.</span></span>            |
| `-ModuleVersion` | <span data-ttu-id="30f86-118">Начиная с PowerShell 5.0, можно указать версию модуля, который должна использовать конфигурация.</span><span class="sxs-lookup"><span data-stu-id="30f86-118">Beginning in PowerShell 5.0, you can specify which version of a module a configuration should use.</span></span> <span data-ttu-id="30f86-119">Дополнительные сведения см. в статье [Импорт определенной версии установленного ресурса](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="30f86-119">For more information, see [Import a specific version of an installed resource](sxsresource.md).</span></span>                                                    |

```powershell
Import-DscResource -ModuleName xActiveDirectory
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="30f86-120">Пример использование Import-DSCResource в конфигурации</span><span class="sxs-lookup"><span data-stu-id="30f86-120">Example: Use Import-DSCResource within a configuration</span></span>

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
    # In PowerShell 5.0 and later, you can specify a ModuleVersion parameter
    Import-DSCResource -ModuleName ComputerManagementDsc -ModuleVersion 6.0.0.0
...
```

> [!NOTE]
> <span data-ttu-id="30f86-121">Указание нескольких значений для имен ресурсов и модулей в одной команде не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="30f86-121">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span>
> <span data-ttu-id="30f86-122">Это может привести к недетерминированному поведению относительно того, с какого ресурса необходимо загружать тот или иной модуль, в случае если один и тот же ресурс существует в нескольких модулях.</span><span class="sxs-lookup"><span data-stu-id="30f86-122">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="30f86-123">Приведенная ниже команда вызовет ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="30f86-123">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="30f86-124">Аспекты, которые следует учитывать при использовании только параметра имени:</span><span class="sxs-lookup"><span data-stu-id="30f86-124">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="30f86-125">Это может быть ресурсоемкая операция в зависимости от количества установленных на компьютере модулей.</span><span class="sxs-lookup"><span data-stu-id="30f86-125">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="30f86-126">Она загрузит первый найденный ресурс с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="30f86-126">It will load the first resource found with the given name.</span></span> <span data-ttu-id="30f86-127">В случае если существует несколько ресурсов с одним именем, она может загрузить не тот ресурс.</span><span class="sxs-lookup"><span data-stu-id="30f86-127">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="30f86-128">Рекомендуется указать `–ModuleName` с параметром `-Name`, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="30f86-128">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="30f86-129">Это обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="30f86-129">This usage has the following benefits:</span></span>

- <span data-ttu-id="30f86-130">Уменьшается влияние на производительность за счет ограничения области поиска для указанного ресурса.</span><span class="sxs-lookup"><span data-stu-id="30f86-130">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="30f86-131">В этом случае явно задается определяющий ресурс модуль, обеспечивая загрузку нужного ресурса.</span><span class="sxs-lookup"><span data-stu-id="30f86-131">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="30f86-132">В PowerShell 5.0 ресурсы DSC могут иметь несколько версий, и эти версии можно устанавливать на компьютере параллельно.</span><span class="sxs-lookup"><span data-stu-id="30f86-132">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="30f86-133">Это реализуется благодаря наличию нескольких версий модуля ресурсов, которые содержатся в одной папке модуля.</span><span class="sxs-lookup"><span data-stu-id="30f86-133">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span> <span data-ttu-id="30f86-134">Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="30f86-134">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="30f86-135">Технология IntelliSense с Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="30f86-135">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="30f86-136">При создании конфигурации DSC в ISE программа PowerShell предоставляет IntelliSence для ресурсов и их свойств.</span><span class="sxs-lookup"><span data-stu-id="30f86-136">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="30f86-137">Определения ресурсов в пути модуля `$pshome` загружаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="30f86-137">Resource definitions under the `$pshome` module path are loaded automatically.</span></span>
<span data-ttu-id="30f86-138">При импорте ресурсов с использованием ключевого слова `Import-DSCResource` добавляются определения указанного ресурса и в Intellisense добавляется схема импортируемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="30f86-138">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![Технология IntelliSense в интегрированной среде сценариев для ресурса DSC](media/import-dscresource/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="30f86-140">Начиная с PowerShell 5.0 в ISE было добавлено завершение нажатием клавиши TAB для ресурсов DSC и их свойств.</span><span class="sxs-lookup"><span data-stu-id="30f86-140">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="30f86-141">Дополнительные сведения см. в статье о [ресурсах DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="30f86-141">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="30f86-142">При компиляции конфигурации PowerShell использует импортированные определения ресурсов, чтобы проверить все блоки ресурсов в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="30f86-142">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span> <span data-ttu-id="30f86-143">Каждый блок ресурсов проверяется с использованием определения схемы ресурса на соответствие следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="30f86-143">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="30f86-144">используются только свойства, определенные в схеме;</span><span class="sxs-lookup"><span data-stu-id="30f86-144">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="30f86-145">типы данных для каждого свойства заданы правильно;</span><span class="sxs-lookup"><span data-stu-id="30f86-145">The data types for each property are correct.</span></span>
- <span data-ttu-id="30f86-146">свойства ключей заданы;</span><span class="sxs-lookup"><span data-stu-id="30f86-146">Keys properties are specified.</span></span>
- <span data-ttu-id="30f86-147">свойство только для чтения не используется;</span><span class="sxs-lookup"><span data-stu-id="30f86-147">No read-only property is used.</span></span>
- <span data-ttu-id="30f86-148">проверка типов сопоставлений значения.</span><span class="sxs-lookup"><span data-stu-id="30f86-148">Validation on value maps types.</span></span>

<span data-ttu-id="30f86-149">Рассмотрим следующую конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="30f86-149">Consider the following configuration:</span></span>

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
            Name = "Telnet-Client"
            Ensure = "Invalid"
        }
    }
}
```

<span data-ttu-id="30f86-150">Компиляция этой конфигурации приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="30f86-150">Compiling this Configuration results in an error.</span></span>

```Output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values 'Invalid' is not supported or
valid for property 'Ensure' on class 'WindowsFeature'. Please specify only supported values:
Present, Absent.
```

<span data-ttu-id="30f86-151">IntelliSense и проверка схемы позволяют обнаруживать больше ошибок во время анализа и компиляции, избегая осложнений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="30f86-151">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="30f86-152">Каждый ресурс DSC может иметь имя и **FriendlyName** , определенное схемой ресурса.</span><span class="sxs-lookup"><span data-stu-id="30f86-152">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="30f86-153">Ниже приведены две первые строки файла MSFT_ServiceResource.shema.mof.</span><span class="sxs-lookup"><span data-stu-id="30f86-153">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
>
> <span data-ttu-id="30f86-154">При использовании этого ресурса в конфигурации можно указать **MSFT_ServiceResource** или **Service**.</span><span class="sxs-lookup"><span data-stu-id="30f86-154">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="30f86-155">Различия PowerShell версий 4 и 5</span><span class="sxs-lookup"><span data-stu-id="30f86-155">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="30f86-156">Существует несколько различий, заметных при создании конфигураций в PowerShell версии 4.0, 5.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="30f86-156">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="30f86-157">В этом разделе освещены различия, которые имеют отношение к этой статье.</span><span class="sxs-lookup"><span data-stu-id="30f86-157">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="30f86-158">Несколько версий ресурсов</span><span class="sxs-lookup"><span data-stu-id="30f86-158">Multiple Resource Versions</span></span>

<span data-ttu-id="30f86-159">Установка нескольких версий ресурсов и их параллельное использование не поддерживаются в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="30f86-159">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="30f86-160">Если вы заметили проблемы при импорте ресурсов в свою конфигурацию, убедитесь, что установлена только одна версия ресурса.</span><span class="sxs-lookup"><span data-stu-id="30f86-160">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="30f86-161">На рисунке ниже показано, что установлены две версии модуля **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="30f86-161">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![Несколько версий ресурсов, установленных в папке](media/import-dscresource/multiple-resource-versions-broken.png)

<span data-ttu-id="30f86-163">Скопируйте содержимое нужной версии модуля на верхний уровень каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="30f86-163">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![Скопируйте нужную версию в каталог модуля верхнего уровня.](media/import-dscresource/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a><span data-ttu-id="30f86-165">Расположение ресурса</span><span class="sxs-lookup"><span data-stu-id="30f86-165">Resource location</span></span>

<span data-ttu-id="30f86-166">При разработке и компилировании конфигураций ваши ресурсы можно хранить в любом каталоге, указанном в параметре [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span><span class="sxs-lookup"><span data-stu-id="30f86-166">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span></span>
<span data-ttu-id="30f86-167">В PowerShell 4.0 диспетчер LCM требовал, чтобы все модули ресурсов DSC хранились по пути Program Files\WindowsPowerShell\Modules или `$pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="30f86-167">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="30f86-168">Начиная с PowerShell 5.0 это требование было удалено, а модули ресурсов могут храниться в любом каталоге, заданном с помощью параметра `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="30f86-168">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

### <a name="moduleversion-added"></a><span data-ttu-id="30f86-169">Добавлен параметр ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="30f86-169">ModuleVersion added</span></span>

<span data-ttu-id="30f86-170">Начиная с версии PowerShell 5.0, параметр `-ModuleVersion` позволяет указать версию модуля для использования в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="30f86-170">Beginning in PowerShell 5.0, the `-ModuleVersion` parameter allows you to specify which version of a module to use within your configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="30f86-171">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="30f86-171">See also</span></span>

- [<span data-ttu-id="30f86-172">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="30f86-172">Resources</span></span>](../resources/resources.md)
