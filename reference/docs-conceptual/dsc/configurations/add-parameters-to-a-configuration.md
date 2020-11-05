---
ms.date: 12/12/2018
keywords: dsc,powershell,resource,gallery,setup
title: Добавление параметров в конфигурацию
description: Конфигурации могут быть параметризованы. Так они становятся более динамичными на основе данных, вводимых пользователем.
ms.openlocfilehash: aea230d34994a7b20076559c44990abe554d5395
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656809"
---
# <a name="add-parameters-to-a-configuration"></a><span data-ttu-id="f5915-104">Добавление параметров в конфигурацию</span><span class="sxs-lookup"><span data-stu-id="f5915-104">Add Parameters to a Configuration</span></span>

<span data-ttu-id="f5915-105">Как и функции, [конфигурации](configurations.md) могут быть параметризованы. Так они становятся более динамичными на основе данных, вводимых пользователем.</span><span class="sxs-lookup"><span data-stu-id="f5915-105">Like Functions, [Configurations](configurations.md) can be parameterized to allow more dynamic configurations based on user input.</span></span> <span data-ttu-id="f5915-106">Шаги похожи на описанные в разделе о [функциях с параметрами](/powershell/module/microsoft.powershell.core/about/about_functions).</span><span class="sxs-lookup"><span data-stu-id="f5915-106">The steps are similar to those described in [Functions with Parameters](/powershell/module/microsoft.powershell.core/about/about_functions).</span></span>

<span data-ttu-id="f5915-107">Этот пример начинается с базовой конфигурации, которая настраивает службу "Диспетчер очереди печати" (Spooler) в состояние Running (Выполняется).</span><span class="sxs-lookup"><span data-stu-id="f5915-107">This example starts with a basic Configuration that configures the "Spooler" service to be "Running".</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a><span data-ttu-id="f5915-108">Встроенные параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="f5915-108">Built-in Configuration parameters</span></span>

<span data-ttu-id="f5915-109">В отличие от функции, атрибут [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) не добавляет функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="f5915-109">Unlike a Function though, the [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) attribute adds no functionality.</span></span> <span data-ttu-id="f5915-110">Помимо [общих параметров](/powershell/module/microsoft.powershell.core/about/about_commonparameters), конфигурации могут также использовать следующие встроенные параметры, не требуя их определения пользователем.</span><span class="sxs-lookup"><span data-stu-id="f5915-110">In addition to [Common Parameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters), Configurations can also use the following built in parameters, without requiring you to define them.</span></span>

|        <span data-ttu-id="f5915-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="f5915-111">Parameter</span></span>        |                                         <span data-ttu-id="f5915-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f5915-112">Description</span></span>                                          |
| ----------------------- | -------------------------------------------------------------------------------------------- |
| `-InstanceName`         | <span data-ttu-id="f5915-113">Используется при определении [составных конфигураций](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="f5915-113">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-DependsOn`            | <span data-ttu-id="f5915-114">Используется при определении [составных конфигураций](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="f5915-114">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-PSDSCRunAsCredential` | <span data-ttu-id="f5915-115">Используется при определении [составных конфигураций](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="f5915-115">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-ConfigurationData`    | <span data-ttu-id="f5915-116">Используется для передачи структурированных [данных конфигурации](configData.md), применяемых в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5915-116">Used to pass in structured [Configuration Data](configData.md) for use in the Configuration.</span></span> |
| `-OutputPath`           | <span data-ttu-id="f5915-117">Используется, чтобы указать, где будет скомпилирован файл \<computername\>.mof.</span><span class="sxs-lookup"><span data-stu-id="f5915-117">Used to specify where your "\<computername\>.mof" file will be compiled</span></span>                      |

## <a name="adding-your-own-parameters-to-configurations"></a><span data-ttu-id="f5915-118">Добавление собственных параметров в конфигурации</span><span class="sxs-lookup"><span data-stu-id="f5915-118">Adding your own parameters to Configurations</span></span>

<span data-ttu-id="f5915-119">Помимо встроенных параметров, вы можете также добавить в конфигурации собственные параметры.</span><span class="sxs-lookup"><span data-stu-id="f5915-119">In addition to the built-in parameters, you can also add your own parameters to your Configurations.</span></span>
<span data-ttu-id="f5915-120">Блок параметров помещается непосредственно в объявлении конфигурации, как и функция.</span><span class="sxs-lookup"><span data-stu-id="f5915-120">The parameter block goes directly inside the Configuration declaration, just like a Function.</span></span> <span data-ttu-id="f5915-121">Блок параметров конфигурации должен быть вне любых объявлений **узла** и выше любых инструкций *import*.</span><span class="sxs-lookup"><span data-stu-id="f5915-121">A Configuration parameter block should be outside any **Node** declarations, and above any *import* statements.</span></span> <span data-ttu-id="f5915-122">Добавив параметры, вы можете сделать конфигурации более надежными и динамическими.</span><span class="sxs-lookup"><span data-stu-id="f5915-122">By adding parameters, you can make your Configurations more robust and dynamic.</span></span>

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a><span data-ttu-id="f5915-123">Добавление параметра ComputerName</span><span class="sxs-lookup"><span data-stu-id="f5915-123">Add a ComputerName parameter</span></span>

<span data-ttu-id="f5915-124">Первым параметром, который можно добавить, является `-Computername`. Так вы сможете динамически компилировать MOF-файл для любого параметра `-Computername`, который передается в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f5915-124">The first parameter you might add is a `-Computername` parameter so you can dynamically compile a ".mof" file for any `-Computername` you pass to your configuration.</span></span> <span data-ttu-id="f5915-125">Аналогично функциям, вы также можете определить значение по умолчанию в случае, если пользователь не передаст значение для параметра `-ComputerName`.</span><span class="sxs-lookup"><span data-stu-id="f5915-125">Like Functions, you can also define a default value, in case the user does not pass in a value for `-ComputerName`</span></span>

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

<span data-ttu-id="f5915-126">Затем в конфигурации вы можете указать параметр `-ComputerName` при определении блока узла.</span><span class="sxs-lookup"><span data-stu-id="f5915-126">Within your configuration, you can then specify your `-ComputerName` parameter when defining your Node block.</span></span>

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a><span data-ttu-id="f5915-127">Вызов конфигурации с параметрами</span><span class="sxs-lookup"><span data-stu-id="f5915-127">Calling your Configuration with parameters</span></span>

<span data-ttu-id="f5915-128">После добавления параметров в конфигурацию их можно использовать так же, как с командлетом.</span><span class="sxs-lookup"><span data-stu-id="f5915-128">After you have added parameters to your Configuration, you can use them just like you would with a cmdlet.</span></span>

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a><span data-ttu-id="f5915-129">Компиляция нескольких MOF-файлов</span><span class="sxs-lookup"><span data-stu-id="f5915-129">Compiling multiple .mof files</span></span>

<span data-ttu-id="f5915-130">Блок узла также может принимать разделенный запятыми список имен компьютеров и будет автоматически создавать MOF-файлы для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="f5915-130">The Node block can also accept a comma-separated list of computer names and will generate ".mof" files for each.</span></span> <span data-ttu-id="f5915-131">Вы также можете запустить приведенный ниже пример для создания MOF-файлов для всех компьютеров, передаваемых параметру `-ComputerName`.</span><span class="sxs-lookup"><span data-stu-id="f5915-131">You can run the following example to generate ".mof" files for all of the computers passed to the `-ComputerName` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String[]]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a><span data-ttu-id="f5915-132">Расширенные параметры в конфигурациях</span><span class="sxs-lookup"><span data-stu-id="f5915-132">Advanced parameters in Configurations</span></span>

<span data-ttu-id="f5915-133">В дополнение к параметру `-ComputerName`, вы можете добавить параметры для имени и состояния службы.</span><span class="sxs-lookup"><span data-stu-id="f5915-133">In addition to a `-ComputerName` parameter, we can add parameters for the service name and state.</span></span>
<span data-ttu-id="f5915-134">В следующем примере добавляется блок параметров с параметром `-ServiceName`. Этот блок используется для динамического определения блока ресурса **Service**.</span><span class="sxs-lookup"><span data-stu-id="f5915-134">The following example adds a parameter block with a `-ServiceName` parameter and uses it to dynamically define the **Service** resource block.</span></span> <span data-ttu-id="f5915-135">В нем также добавляется параметр `-State` для динамического определения **состояния** в блоке ресурса **Service**.</span><span class="sxs-lookup"><span data-stu-id="f5915-135">It also adds a `-State` parameter to dynamically define the **State** in the **Service** resource block.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="f5915-136">В расширенных сценариях может быть более целесообразно переместить динамические данные в структурированные [данные конфигурации](configData.md).</span><span class="sxs-lookup"><span data-stu-id="f5915-136">In more advanced scenarios, it might make more sense to move your dynamic data into a structured [Configuration Data](configData.md).</span></span>

<span data-ttu-id="f5915-137">Этот пример конфигурации теперь принимает динамическое значение `$ServiceName`, но если оно не задано, компиляция приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="f5915-137">The example Configuration now takes a dynamic `$ServiceName`, but if one is not specified, compiling results in an error.</span></span> <span data-ttu-id="f5915-138">Вы также можете добавить значение по умолчанию, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f5915-138">You could add a default value like this example.</span></span>

```powershell
[String]
$ServiceName="Spooler"
```

<span data-ttu-id="f5915-139">Хотя в этом экземпляре может быть более целесообразно просто заставить пользователя указать значение для параметра `$ServiceName`.</span><span class="sxs-lookup"><span data-stu-id="f5915-139">In this instance though, it makes more sense to simply force the user to specify a value for the `$ServiceName` parameter.</span></span> <span data-ttu-id="f5915-140">Атрибут `parameter` позволяет добавлять дополнительную поддержку проверки и конвейера для параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5915-140">The `parameter` attribute allows you to add further validation and pipeline support to your Configuration's parameters.</span></span>

<span data-ttu-id="f5915-141">Над какими-либо объявлениями параметров добавьте блок атрибутов `parameter`, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="f5915-141">Above any parameter declaration, add the `parameter` attribute block as in the example below.</span></span>

```powershell
[parameter()]
[String]
$ServiceName
```

<span data-ttu-id="f5915-142">Вы можете указать аргументы для каждого атрибута `parameter`, чтобы управлять аспектами определенного параметра.</span><span class="sxs-lookup"><span data-stu-id="f5915-142">You can specify arguments to each `parameter` attribute, to control aspects of the defined parameter.</span></span> <span data-ttu-id="f5915-143">В следующем примере параметр `$ServiceName` изменяется на **обязательный**.</span><span class="sxs-lookup"><span data-stu-id="f5915-143">The following example makes the `$ServiceName` a **Mandatory** parameter.</span></span>

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

<span data-ttu-id="f5915-144">Для параметра `$State` мы бы хотели запретить пользователю указывать значения за пределами предопределенного набора (например, Running, Stopped). Атрибут `ValidationSet*` будет запрещать пользователю указывать значения за пределами определенного набора (например, Running, Stopped).</span><span class="sxs-lookup"><span data-stu-id="f5915-144">For the `$State` parameter, we would like to prevent the user from specifying values outside of a predefined set (like Running, Stopped) the `ValidationSet*`attribute would prevent the user from specifying values outside of a predefined set (like Running, Stopped).</span></span> <span data-ttu-id="f5915-145">В следующем примере добавляется атрибут `ValidationSet` для параметра `$State`.</span><span class="sxs-lookup"><span data-stu-id="f5915-145">The following example adds the `ValidationSet` attribute to the `$State` parameter.</span></span> <span data-ttu-id="f5915-146">Так как мы не хотим изменять параметр `$State` на **обязательный** , нам нужно будет добавить для него значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5915-146">Since we do not want to make the `$State` parameter **Mandatory** , we will need to add a default value for it.</span></span>

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> <span data-ttu-id="f5915-147">Вам не нужно указывать атрибут `parameter` при использовании атрибута `validation`.</span><span class="sxs-lookup"><span data-stu-id="f5915-147">You do not need to specify a `parameter` attribute when using a `validation` attribute.</span></span>

<span data-ttu-id="f5915-148">Дополнительные сведения об атрибуте `parameter` и атрибутах проверки см. в разделе о [расширенных параметрах функций](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span><span class="sxs-lookup"><span data-stu-id="f5915-148">You can read more about the `parameter` and validation attributes in [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span></span>

## <a name="fully-parameterized-configuration"></a><span data-ttu-id="f5915-149">Полностью параметризованная конфигурация</span><span class="sxs-lookup"><span data-stu-id="f5915-149">Fully parameterized Configuration</span></span>

<span data-ttu-id="f5915-150">Теперь у нас есть параметризованная конфигурация, которая вынуждает пользователя указывать параметры `-InstanceName`, `-ServiceName` и проверяет параметр `-State`.</span><span class="sxs-lookup"><span data-stu-id="f5915-150">We now have a parameterized Configuration that forces the user to specify an `-InstanceName`, `-ServiceName`, and validates the `-State` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost",
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f5915-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5915-151">See also</span></span>

- [<span data-ttu-id="f5915-152">Создание справки по конфигурациям DSC</span><span class="sxs-lookup"><span data-stu-id="f5915-152">Write help for DSC configurations</span></span>](configHelp.md)
- [<span data-ttu-id="f5915-153">Условные операторы и циклы в конфигурациях</span><span class="sxs-lookup"><span data-stu-id="f5915-153">Dynamic Configurations</span></span>](flow-control-in-configurations.md)
- <span data-ttu-id="f5915-154">[Using configuration data in DSC](configData.md) (Использование данных конфигурации в DSC)</span><span class="sxs-lookup"><span data-stu-id="f5915-154">[Use Configuration Data in your Configurations](configData.md)</span></span>
- [<span data-ttu-id="f5915-155">Разделение данных конфигурации и данных среды</span><span class="sxs-lookup"><span data-stu-id="f5915-155">Separate configuration and environment data</span></span>](separatingEnvData.md)
