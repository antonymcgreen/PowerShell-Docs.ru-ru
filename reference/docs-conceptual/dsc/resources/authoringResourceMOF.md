---
ms.date: 07/08/2020
keywords: dsc,powershell,конфигурация,установка
title: Написание пользовательских ресурсов DSC с использованием MOF
description: В этой статье определена схема для настраиваемого ресурса DSC в файле MOF и описана реализаций ресурса в файле скрипта PowerShell.
ms.openlocfilehash: e79a37699c468b2c55c307c96f1c193a2c1595b3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667187"
---
# <a name="writing-a-custom-dsc-resource-with-mof"></a><span data-ttu-id="58cec-104">Написание пользовательских ресурсов DSC с использованием MOF</span><span class="sxs-lookup"><span data-stu-id="58cec-104">Writing a custom DSC resource with MOF</span></span>

> <span data-ttu-id="58cec-105">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="58cec-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="58cec-106">С помощью инструкций из этой статьи мы определим схему для настраиваемого ресурса Desired State Configuration (DSC) Windows PowerShell в MOF-файле и реализуем этот ресурс в файле скрипта Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58cec-106">In this article, we will define the schema for a Windows PowerShell Desired State Configuration (DSC) custom resource in a MOF file, and implement the resource in a Windows PowerShell script file.</span></span>
<span data-ttu-id="58cec-107">Этот ресурс применяется для создания и обслуживания веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="58cec-107">This custom resource is for creating and maintaining a web site.</span></span>

## <a name="creating-the-mof-schema"></a><span data-ttu-id="58cec-108">Создание схемы MOF</span><span class="sxs-lookup"><span data-stu-id="58cec-108">Creating the MOF schema</span></span>

<span data-ttu-id="58cec-109">Схема определяет свойства ресурса, которые можно настроить с помощью сценария DSC.</span><span class="sxs-lookup"><span data-stu-id="58cec-109">The schema defines the properties of your resource that can be configured by a DSC configuration script.</span></span>

### <a name="folder-structure-for-a-mof-resource"></a><span data-ttu-id="58cec-110">Структура папок для ресурса MOF</span><span class="sxs-lookup"><span data-stu-id="58cec-110">Folder structure for a MOF resource</span></span>

<span data-ttu-id="58cec-111">Для реализации настраиваемого ресурса DSC в схеме MOF создайте указанную ниже структуру папок.</span><span class="sxs-lookup"><span data-stu-id="58cec-111">To implement a DSC custom resource with a MOF schema, create the following folder structure.</span></span> <span data-ttu-id="58cec-112">Схема MOF определяется в файле `Demo_IISWebsite.schema.mof`, а скрипт ресурсов определяется в `Demo_IISWebsite.psm1`.</span><span class="sxs-lookup"><span data-stu-id="58cec-112">The MOF schema is defined in the file `Demo_IISWebsite.schema.mof`, and the resource script is defined in `Demo_IISWebsite.psm1`.</span></span> <span data-ttu-id="58cec-113">При необходимости можно создать файл манифеста (PSD1) для модуля.</span><span class="sxs-lookup"><span data-stu-id="58cec-113">Optionally, you can create a module manifest (psd1) file.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResources (folder)
        |- DSCResources (folder)
            |- Demo_IISWebsite (folder)
                |- Demo_IISWebsite.psd1 (file, optional)
                |- Demo_IISWebsite.psm1 (file, required)
                |- Demo_IISWebsite.schema.mof (file, required)
```

> [!NOTE]
> <span data-ttu-id="58cec-114">Папку DSCResources необходимо создать в папке верхнего уровня, а имя папки для каждого ресурса должно совпадать с именем ресурса.</span><span class="sxs-lookup"><span data-stu-id="58cec-114">It is necessary to create a folder named DSCResources under the top-level folder, and that the folder for each resource must have the same name as the resource.</span></span>

### <a name="the-contents-of-the-mof-file"></a><span data-ttu-id="58cec-115">Содержание MOF-файла</span><span class="sxs-lookup"><span data-stu-id="58cec-115">The contents of the MOF file</span></span>

<span data-ttu-id="58cec-116">Приведем пример файла MOF, который можно использовать как настраиваемый ресурс веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="58cec-116">Following is an example MOF file that can be used for a custom website resource.</span></span> <span data-ttu-id="58cec-117">Чтобы воспользоваться этим примером, сохраните данную схему в файле с именем `Demo_IISWebsite.schema.mof`.</span><span class="sxs-lookup"><span data-stu-id="58cec-117">To follow this example, save this schema to a file, and call the file `Demo_IISWebsite.schema.mof`.</span></span>

```
[ClassVersion("1.0.0"), FriendlyName("Website")]
class Demo_IISWebsite : OMI_BaseResource
{
  [Key] string Name;
  [Required] string PhysicalPath;
  [write,ValueMap{"Present", "Absent"},Values{"Present", "Absent"}] string Ensure;
  [write,ValueMap{"Started","Stopped"},Values{"Started", "Stopped"}] string State;
  [write] string Protocol[];
  [write] string BindingInfo[];
  [write] string ApplicationPool;
  [read] string ID;
};
```

<span data-ttu-id="58cec-118">В представленном выше коде обратите внимание на следующее.</span><span class="sxs-lookup"><span data-stu-id="58cec-118">Note the following about the previous code:</span></span>

- <span data-ttu-id="58cec-119">`FriendlyName` определяет имя, которое можно использовать для ссылки на этот настраиваемый ресурс в сценариях DSC.</span><span class="sxs-lookup"><span data-stu-id="58cec-119">`FriendlyName` defines the name you can use to refer to this custom resource in DSC configuration scripts.</span></span> <span data-ttu-id="58cec-120">В этом примере `Website` — эквивалент понятного имени `Archive` для встроенного ресурса архива.</span><span class="sxs-lookup"><span data-stu-id="58cec-120">In this example, `Website` is equivalent to the friendly name `Archive` for the built-in Archive resource.</span></span>
- <span data-ttu-id="58cec-121">Класс, определяемый для настраиваемого ресурса, должен быть производным от `OMI_BaseResource`.</span><span class="sxs-lookup"><span data-stu-id="58cec-121">The class you define for your custom resource must derive from `OMI_BaseResource`.</span></span>
- <span data-ttu-id="58cec-122">Квалификатор типа `[Key]` в свойстве означает, что это свойство служит для уникальной идентификации экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="58cec-122">The type qualifier, `[Key]`, on a property indicates that this property will uniquely identify the resource instance.</span></span> <span data-ttu-id="58cec-123">Необходимо указать по крайней мере одно свойство `[Key]`.</span><span class="sxs-lookup"><span data-stu-id="58cec-123">At least one `[Key]` property is required.</span></span>
- <span data-ttu-id="58cec-124">Квалификатор `[Required]` означает, что свойство является обязательным (значение необходимо указывать в любом сценарии настройки, где используется ресурс).</span><span class="sxs-lookup"><span data-stu-id="58cec-124">The `[Required]` qualifier indicates that the property is required (a value must be specified in any configuration script that uses this resource).</span></span>
- <span data-ttu-id="58cec-125">Квалификатор `[write]` означает, что свойство не является обязательным при использовании настраиваемого ресурса в сценарии настройки.</span><span class="sxs-lookup"><span data-stu-id="58cec-125">The `[write]` qualifier indicates that this property is optional when using the custom resource in a configuration script.</span></span> <span data-ttu-id="58cec-126">Квалификатор `[read]` означает, что свойство не может задаваться конфигурацией и предназначено только для целей отчетности.</span><span class="sxs-lookup"><span data-stu-id="58cec-126">The `[read]` qualifier indicates that a property cannot be set by a configuration, and is for reporting purposes only.</span></span>
- <span data-ttu-id="58cec-127">`Values` ограничивает значения, которые могут быть присвоены свойству, списком значений, определенных в `ValueMap`.</span><span class="sxs-lookup"><span data-stu-id="58cec-127">`Values` restricts the values that can be assigned to the property to the list of values defined in `ValueMap`.</span></span> <span data-ttu-id="58cec-128">Дополнительные сведения см. в статье [ValueMap и квалификаторы значений](/windows/desktop/WmiSdk/value-map).</span><span class="sxs-lookup"><span data-stu-id="58cec-128">For more information, see [ValueMap and Value Qualifiers](/windows/desktop/WmiSdk/value-map).</span></span>
- <span data-ttu-id="58cec-129">Для сохранения единообразия встроенных ресурсов DSC рекомендуется включать в ресурс свойство `Ensure` с значениями `Present` и `Absent`.</span><span class="sxs-lookup"><span data-stu-id="58cec-129">Including a property called `Ensure` with values `Present` and `Absent` in your resource is recommended as a way to maintain a consistent style with built-in DSC resources.</span></span>
- <span data-ttu-id="58cec-130">Имя настраиваемого ресурса должно иметь формат `classname.schema.mof`, где `classname` — это идентификатор, следующий за ключевым словом `class` в определении схемы.</span><span class="sxs-lookup"><span data-stu-id="58cec-130">Name the schema file for your custom resource as follows: `classname.schema.mof`, where `classname` is the identifier that follows the `class` keyword in your schema definition.</span></span>

### <a name="writing-the-resource-script"></a><span data-ttu-id="58cec-131">Создание сценария ресурсов</span><span class="sxs-lookup"><span data-stu-id="58cec-131">Writing the resource script</span></span>

<span data-ttu-id="58cec-132">Сценарий ресурса реализует логику ресурса.</span><span class="sxs-lookup"><span data-stu-id="58cec-132">The resource script implements the logic of the resource.</span></span> <span data-ttu-id="58cec-133">В этот модуль необходимо включить три функции: `Get-TargetResource`, `Set-TargetResource` и `Test-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="58cec-133">In this module, you must include three functions called `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource`.</span></span> <span data-ttu-id="58cec-134">Все три функции должны принимать набор параметров, идентичный набору свойств, заданных в схеме MOF для вашего ресурса.</span><span class="sxs-lookup"><span data-stu-id="58cec-134">All three functions must take a parameter set that is identical to the set of properties defined in the MOF schema that you created for your resource.</span></span> <span data-ttu-id="58cec-135">В этом документе такой набор свойств называется "свойства ресурса".</span><span class="sxs-lookup"><span data-stu-id="58cec-135">In this document, this set of properties is referred to as the "resource properties."</span></span> <span data-ttu-id="58cec-136">Сохраните эти три функции в файл с именем `<ResourceName>.psm1`.</span><span class="sxs-lookup"><span data-stu-id="58cec-136">Store these three functions in a file called `<ResourceName>.psm1`.</span></span> <span data-ttu-id="58cec-137">В следующем примере функции сохраняются в файл с именем `Demo_IISWebsite.psm1`.</span><span class="sxs-lookup"><span data-stu-id="58cec-137">In the following example, the functions are stored in a file called `Demo_IISWebsite.psm1`.</span></span>

> [!NOTE]
> <span data-ttu-id="58cec-138">Многократное выполнение одного и того же сценария настройки для ресурса не вызывает ошибок, а состояние ресурса остается таким же, как при однократном выполнении.</span><span class="sxs-lookup"><span data-stu-id="58cec-138">When you run the same configuration script on your resource more than once, you should receive no errors and the resource should remain in the same state as running the script once.</span></span> <span data-ttu-id="58cec-139">Для этого функции `Get-TargetResource` и `Test-TargetResource` не должны изменять ресурс, а вызов функции `Set-TargetResource` с одними и теми же параметрами больше одного раза подряд должен быть эквивалентен однократному вызову этой функции.</span><span class="sxs-lookup"><span data-stu-id="58cec-139">To accomplish this, ensure that your `Get-TargetResource` and `Test-TargetResource` functions leave the resource unchanged, and that invoking the `Set-TargetResource` function more than once in a sequence with the same parameter values is always equivalent to invoking it once.</span></span>

<span data-ttu-id="58cec-140">В реализации функции `Get-TargetResource` используйте значения свойств основных ресурсов, предоставляемых в качестве параметров, для проверки состояния указанного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="58cec-140">In the `Get-TargetResource` function implementation, use the key resource property values that are provided as parameters to check the status of the specified resource instance.</span></span> <span data-ttu-id="58cec-141">Эта функция должна возвращать хэш-таблицу со списком всех свойств ресурса в виде ключей и фактических значений этих свойств в виде соответствующих значений.</span><span class="sxs-lookup"><span data-stu-id="58cec-141">This function must return a hash table that lists all the resource properties as keys and the actual values of these properties as the corresponding values.</span></span> <span data-ttu-id="58cec-142">Пример кода:</span><span class="sxs-lookup"><span data-stu-id="58cec-142">The following code provides an example.</span></span>

```powershell
# DSC uses the Get-TargetResource function to fetch the status of the resource instance
# specified in the parameters for the target machine
function Get-TargetResource
{
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

        $getTargetResourceResult = $null;

        <#
          Insert logic that uses the mandatory parameter values to get the website and
          assign it to a variable called $Website
          Set $ensureResult to "Present" if the requested website exists and to "Absent" otherwise
        #>

        # Add all Website properties to the hash table
        # This simple example assumes that $Website is not null
        $getTargetResourceResult = @{
            Name = $Website.Name
            Ensure = $ensureResult
            PhysicalPath = $Website.physicalPath
            State = $Website.state
            ID = $Website.id
            ApplicationPool = $Website.applicationPool
            Protocol = $Website.bindings.Collection.protocol
            Binding = $Website.bindings.Collection.bindingInformation
        }

        $getTargetResourceResult
}
```

<span data-ttu-id="58cec-143">В зависимости от того, какие значения заданы для свойств ресурса в сценарии конфигурации, `Set-TargetResource` должен выполнять одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="58cec-143">Depending on the values that are specified for the resource properties in the configuration script, the `Set-TargetResource` must do one of the following:</span></span>

- <span data-ttu-id="58cec-144">Создание веб-сайта</span><span class="sxs-lookup"><span data-stu-id="58cec-144">Create a new website</span></span>
- <span data-ttu-id="58cec-145">Обновление существующего веб-сайта</span><span class="sxs-lookup"><span data-stu-id="58cec-145">Update an existing website</span></span>
- <span data-ttu-id="58cec-146">Удаление существующего веб-сайта</span><span class="sxs-lookup"><span data-stu-id="58cec-146">Delete an existing website</span></span>

<span data-ttu-id="58cec-147">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="58cec-147">The following example illustrates this.</span></span>

```powershell
# The Set-TargetResource function is used to create, delete or configure a website on the target machine.
function Set-TargetResource
{
    [CmdletBinding(SupportsShouldProcess=$true)]
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

    <#
        If Ensure is set to "Present" and the website specified in the mandatory input parameters
          does not exist, then create it using the specified parameter values
        Else, if Ensure is set to "Present" and the website does exist, then update its properties
          to match the values provided in the non-mandatory parameter values
        Else, if Ensure is set to "Absent" and the website does not exist, then do nothing
        Else, if Ensure is set to "Absent" and the website does exist, then delete the website
    #>
}
```

<span data-ttu-id="58cec-148">И наконец, функция `Test-TargetResource` должна принимать тот же набор параметров, что и функции `Get-TargetResource` и `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="58cec-148">Finally, the `Test-TargetResource` function must take the same parameter set as `Get-TargetResource` and `Set-TargetResource`.</span></span> <span data-ttu-id="58cec-149">В собственной реализации функции `Test-TargetResource` проверьте состояние экземпляра ресурса, заданное основными параметрами.</span><span class="sxs-lookup"><span data-stu-id="58cec-149">In your implementation of `Test-TargetResource`, check the status of the resource instance that is specified in the key parameters.</span></span> <span data-ttu-id="58cec-150">Если фактическое состояние экземпляра ресурса не соответствует значениям, указанным в наборе параметров, возвращается `$false`.</span><span class="sxs-lookup"><span data-stu-id="58cec-150">If the actual status of the resource instance does not match the values specified in the parameter set, return `$false`.</span></span> <span data-ttu-id="58cec-151">В противном случае возвращается `$true`.</span><span class="sxs-lookup"><span data-stu-id="58cec-151">Otherwise, return `$true`.</span></span>

<span data-ttu-id="58cec-152">Следующий код реализует функцию `Test-TargetResource`:</span><span class="sxs-lookup"><span data-stu-id="58cec-152">The following code implements the `Test-TargetResource` function.</span></span>

```powershell
function Test-TargetResource
{
    [CmdletBinding()]
    [OutputType([System.Boolean])]
    param
    (
        [ValidateSet("Present","Absent")]
        [System.String]
        $Ensure,

        [parameter(Mandatory = $true)]
        [System.String]
        $Name,

        [parameter(Mandatory = $true)]
        [System.String]
        $PhysicalPath,

        [ValidateSet("Started","Stopped")]
        [System.String]
        $State,

        [System.String[]]
        $Protocol,

        [System.String[]]
        $BindingData,

        [System.String]
        $ApplicationPool
    )

    # Get the current state
    $currentState = Get-TargetResource -Ensure $Ensure -Name $Name -PhysicalPath $PhysicalPath -State $State -ApplicationPool $ApplicationPool -BindingInfo $BindingInfo -Protocol $Protocol

    # Write-Verbose "Use this cmdlet to deliver information about command processing."

    # Write-Debug "Use this cmdlet to write debug information while troubleshooting."

    # Include logic to
    $result = [System.Boolean]
    # Add logic to test whether the website is present and its status matches the supplied
    # parameter values. If it does, return true. If it does not, return false.
    $result
}
```

> [!NOTE]
> <span data-ttu-id="58cec-153">Чтобы упростить отладку, используйте в реализации трех предыдущих функций командлет `Write-Verbose`.</span><span class="sxs-lookup"><span data-stu-id="58cec-153">For easier debugging, use the `Write-Verbose` cmdlet in your implementation of the previous three functions.</span></span> <span data-ttu-id="58cec-154">Он записывает текст в поток подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="58cec-154">This cmdlet writes text to the verbose message stream.</span></span> <span data-ttu-id="58cec-155">По умолчанию поток подробных сообщений не отображается, однако его можно вывести на экран, изменив значение переменной **$VerbosePreference** или применив в командлетах DSC параметр **Verbose** со значением new.</span><span class="sxs-lookup"><span data-stu-id="58cec-155">By default, the verbose message stream is not displayed, but you can display it by changing the value of the **$VerbosePreference** variable or by using the **Verbose** parameter in the DSC cmdlets = new.</span></span>

### <a name="creating-the-module-manifest"></a><span data-ttu-id="58cec-156">Создание манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="58cec-156">Creating the module manifest</span></span>

<span data-ttu-id="58cec-157">Наконец, используйте командлет `New-ModuleManifest`, чтобы определить файл `<ResourceName>.psd1` для модуля вашего настраиваемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="58cec-157">Finally, use the `New-ModuleManifest` cmdlet to define a `<ResourceName>.psd1` file for your custom resource module.</span></span> <span data-ttu-id="58cec-158">При вызове этого командлета необходимо сослаться на модуль сценария (PSM1-файл), описанный в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="58cec-158">When you invoke this cmdlet, reference the script module (.psm1) file described in the previous section.</span></span> <span data-ttu-id="58cec-159">Включите в список функций для экспорта функции `Get-TargetResource`, `Set-TargetResource` и `Test-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="58cec-159">Include `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` in the list of functions to export.</span></span> <span data-ttu-id="58cec-160">Пример файла манифеста:</span><span class="sxs-lookup"><span data-stu-id="58cec-160">Following is an example manifest file.</span></span>

```powershell
# Module manifest for module 'Demo.IIS.Website'
#
# Generated on: 1/10/2013
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '6AB5ED33-E923-41d8-A3A4-5ADDA2B301DE'

# Author of this module
Author = 'Contoso'

# Company or vendor of this module
CompanyName = 'Contoso'

# Copyright statement for this module
Copyright = 'Contoso. All rights reserved.'

# Description of the functionality provided by this module
Description = 'This Module is used to support the creation and configuration of IIS Websites through Get, Set and Test API on the DSC managed nodes.'

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '4.0'

# Minimum version of the common language runtime (CLR) required by this module
CLRVersion = '4.0'

# Modules that must be imported into the global environment prior to importing this module
RequiredModules = @("WebAdministration")

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
NestedModules = @("Demo_IISWebsite.psm1")

# Functions to export from this module
FunctionsToExport = @("Get-TargetResource", "Set-TargetResource", "Test-TargetResource")

# Cmdlets to export from this module
#CmdletsToExport = '*'

# HelpInfo URI of this module
# HelpInfoURI = ''
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="58cec-161">Поддержка PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="58cec-161">Supporting PsDscRunAsCredential</span></span>

> [!Note]
> <span data-ttu-id="58cec-162">**PsDscRunAsCredential** поддерживается в PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="58cec-162">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="58cec-163">Свойство **PsDscRunAsCredential** может использоваться в блоке ресурса [конфигураций DSC](../configurations/configurations.md), чтобы указать, что ресурс должен выполняться с указанным набором учетных данных.</span><span class="sxs-lookup"><span data-stu-id="58cec-163">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="58cec-164">Дополнительные сведения см. в разделе [Запуск DSC с учетными данными пользователя](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="58cec-164">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="58cec-165">Чтобы получить доступ к пользовательскому контексту из настраиваемого ресурса, можно использовать автоматическую переменную `$PsDscContext`.</span><span class="sxs-lookup"><span data-stu-id="58cec-165">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="58cec-166">Например, следующий код пропишет пользовательский контекст, по которому выполняется ресурс, в подробный выходной поток:</span><span class="sxs-lookup"><span data-stu-id="58cec-166">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="rebooting-the-node"></a><span data-ttu-id="58cec-167">Перезагрузка узла</span><span class="sxs-lookup"><span data-stu-id="58cec-167">Rebooting the Node</span></span>

<span data-ttu-id="58cec-168">Если действия, предпринятые в вашей функции `Set-TargetResource`, требуют перезагрузки, можно использовать глобальный флаг, чтобы заставить LCM перезапустить узел.</span><span class="sxs-lookup"><span data-stu-id="58cec-168">If the actions taken in your `Set-TargetResource` function require a reboot, you can use a global flag to tell the LCM to reboot the Node.</span></span> <span data-ttu-id="58cec-169">Перезагрузка происходит непосредственно после выполнения функции `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="58cec-169">This reboot occurs directly after the `Set-TargetResource` function completes.</span></span>

<span data-ttu-id="58cec-170">Внутри вашей функции `Set-TargetResource` добавьте следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="58cec-170">Inside your `Set-TargetResource` function, add the following line of code.</span></span>

```powershell
# Include this line if the resource requires a system reboot.
$global:DSCMachineStatus = 1
```

<span data-ttu-id="58cec-171">Чтобы LCM перезапустил узел, флаг **RebootNodeIfNeeded** необходимо задать как `$true`.</span><span class="sxs-lookup"><span data-stu-id="58cec-171">In order for the LCM to reboot the Node, the **RebootNodeIfNeeded** flag needs to be set to `$true`.</span></span>
<span data-ttu-id="58cec-172">Параметр **ActionAfterReboot** также должен быть равен **ContinueConfiguration** ; это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58cec-172">The **ActionAfterReboot** setting should also be set to **ContinueConfiguration** , which is the default.</span></span> <span data-ttu-id="58cec-173">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md) или [Настройка локального диспетчера конфигураций (версия 4)](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="58cec-173">For more information on configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configuring the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>
