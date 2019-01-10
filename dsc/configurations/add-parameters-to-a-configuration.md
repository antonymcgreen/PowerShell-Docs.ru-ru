---
ms.date: 12/12/2018
keywords: DSC, powershell, ресурсов, в коллекции, программа установки
title: Добавление параметров в конфигурацию
ms.openlocfilehash: 15213404f0cdd6416baf1f83af91b8f5279cc97f
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402555"
---
# <a name="add-parameters-to-a-configuration"></a><span data-ttu-id="f1f9c-103">Добавление параметров в конфигурацию</span><span class="sxs-lookup"><span data-stu-id="f1f9c-103">Add Parameters to a Configuration</span></span>

<span data-ttu-id="f1f9c-104">Аналогично функциям, [конфигураций](configurations.md) могут быть параметризованы, чтобы разрешить более динамической конфигурации, на основе ввода пользователя.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-104">Like Functions, [Configurations](configurations.md) can be parameterized to allow more dynamic configurations based on user input.</span></span> <span data-ttu-id="f1f9c-105">Шаги похожи на описанные в [функции с параметрами](/powershell/module/microsoft.powershell.core/about/about_functions).</span><span class="sxs-lookup"><span data-stu-id="f1f9c-105">The steps are similar to those described in [Functions with Parameters](/powershell/module/microsoft.powershell.core/about/about_functions).</span></span>

<span data-ttu-id="f1f9c-106">В этом примере запускается с базовую конфигурацию, которая настраивает службу «Spooler», «Выполняется».</span><span class="sxs-lookup"><span data-stu-id="f1f9c-106">This example starts with a basic Configuration that configures the "Spooler" service to be "Running".</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to implicitly import any required resources or modules.
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

## <a name="built-in-configuration-parameters"></a><span data-ttu-id="f1f9c-107">Встроенные параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f9c-107">Built-in Configuration parameters</span></span>

<span data-ttu-id="f1f9c-108">В отличие от функции, [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) атрибут добавляет функциональные возможности отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-108">Unlike a Function though, the [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) attribute adds no functionality.</span></span> <span data-ttu-id="f1f9c-109">В дополнение к [общих параметров](/powershell/module/microsoft.powershell.core/about/about_commonparameters), конфигурации можно также использовать следующие встроенные параметры, не требуя их определения.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-109">In addition to [Common Parameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters), Configurations can also use the following built in parameters, without requiring you to define them.</span></span>

|<span data-ttu-id="f1f9c-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="f1f9c-110">Parameter</span></span>  |<span data-ttu-id="f1f9c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f1f9c-111">Description</span></span>  |
|---------|---------|
|`-InstanceName`|<span data-ttu-id="f1f9c-112">Использовать при определении [составного конфигурации](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="f1f9c-112">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>|
|`-DependsOn`|<span data-ttu-id="f1f9c-113">Использовать при определении [составного конфигурации](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="f1f9c-113">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>|
|`-PSDSCRunAsCredential`|<span data-ttu-id="f1f9c-114">Использовать при определении [составного конфигурации](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="f1f9c-114">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>|
|`-ConfigurationData`|<span data-ttu-id="f1f9c-115">Используется для передачи в структурированный [данные конфигурации](configData.md) для использования в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-115">Used to pass in structured [Configuration Data](configData.md) for use in the Configuration.</span></span>|
|`-OutputPath`|<span data-ttu-id="f1f9c-116">Используется, чтобы указать, где в «\<computername\>.mof» компиляции файла</span><span class="sxs-lookup"><span data-stu-id="f1f9c-116">Used to specify where your "\<computername\>.mof" file will be compiled</span></span>|

## <a name="adding-your-own-parameters-to-configurations"></a><span data-ttu-id="f1f9c-117">Добавление собственных параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f9c-117">Adding your own parameters to Configurations</span></span>

<span data-ttu-id="f1f9c-118">Помимо встроенных параметров можно также добавить собственные параметры для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-118">In addition to the built-in parameters, you can also add your own parameters to your Configurations.</span></span> <span data-ttu-id="f1f9c-119">Блок параметров переходит непосредственно в объявлении конфигурации, так же, как функции.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-119">The parameter block goes directly inside the Configuration declaration, just like a Function.</span></span> <span data-ttu-id="f1f9c-120">Блок параметров конфигурации должны быть вне любого **узел** объявления и более поздних версий, любой *импорта* инструкций.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-120">A Configuration parameter block should be outside any **Node** declarations, and above any *import* statements.</span></span> <span data-ttu-id="f1f9c-121">Добавив параметры, конфигурации можно сделать более надежным и динамические.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-121">By adding parameters, you can make your Configurations more robust and dynamic.</span></span>

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a><span data-ttu-id="f1f9c-122">Добавьте параметр ComputerName</span><span class="sxs-lookup"><span data-stu-id="f1f9c-122">Add a ComputerName parameter</span></span>

<span data-ttu-id="f1f9c-123">Первый параметр, можно добавить является `-Computername` параметра, поэтому может динамически компилировать MOF «-» файла для любого `-Computername` передать в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-123">The first parameter you might add is a `-Computername` parameter so you can dynamically compile a ".mof" file for any `-Computername` you pass to your configuration.</span></span> <span data-ttu-id="f1f9c-124">Как и функции можно также определить значение по умолчанию, в случае, если пользователь не передать значение для `-ComputerName`</span><span class="sxs-lookup"><span data-stu-id="f1f9c-124">Like Functions, you can also define a default value, in case the user does not pass in a value for `-ComputerName`</span></span>

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

<span data-ttu-id="f1f9c-125">В конфигурацию, можно затем указать ваш `-ComputerName` параметров при определении в блоке узла.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-125">Within your configuration, you can then specify your `-ComputerName` parameter when defining your Node block.</span></span>

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a><span data-ttu-id="f1f9c-126">Вызов конфигурации с параметрами</span><span class="sxs-lookup"><span data-stu-id="f1f9c-126">Calling your Configuration with parameters</span></span>

<span data-ttu-id="f1f9c-127">После добавления параметров конфигурации, их можно использовать так же, как с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-127">After you have added parameters to your Configuration, you can use them just like you would with a cmdlet.</span></span>

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a><span data-ttu-id="f1f9c-128">Компиляция нескольких файлы MOF</span><span class="sxs-lookup"><span data-stu-id="f1f9c-128">Compiling multiple .mof files</span></span>

<span data-ttu-id="f1f9c-129">В блоке узла также может принять разделенный запятыми список имен компьютеров и автоматически создаст MOF-файлы для каждого.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-129">The Node block can also accept a comma-separated list of computer names and will generate ".mof" files for each.</span></span> <span data-ttu-id="f1f9c-130">Можно запустить приведенный ниже, для создания MOF-файлы для всех компьютеров, передаваемый `-ComputerName` параметра.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-130">You can run the following example to generate ".mof" files for all of the computers passed to the `-ComputerName` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ComputerName="localhost"
    )

    # It is best practice to implicitly import any required resources or modules.
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

## <a name="advanced-parameters-in-configurations"></a><span data-ttu-id="f1f9c-131">Дополнительные параметры в конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f9c-131">Advanced parameters in Configurations</span></span>

<span data-ttu-id="f1f9c-132">В дополнение к `-ComputerName` параметр, можно добавить параметры для имени службы и состояние.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-132">In addition to a `-ComputerName` parameter, we can add parameters for the service name and state.</span></span> <span data-ttu-id="f1f9c-133">В следующем примере добавляется параметр блок с `-ServiceName` параметр и использует его для динамического определения **службы** блоке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-133">The following example adds a parameter block with a `-ServiceName` parameter and uses it to dynamically define the **Service** resource block.</span></span> <span data-ttu-id="f1f9c-134">Он также добавляет `-State` параметр для динамического определения **состояние** в **службы** блоке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-134">It also adds a `-State` parameter to dynamically define the **State** in the **Service** resource block.</span></span>

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

    # It is best practice to implicitly import any required resources or modules.
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
> <span data-ttu-id="f1f9c-135">В различных сценариях advacned, может быть более целесообразно для перемещения динамических данных в структурированной [данные конфигурации](configData.md).</span><span class="sxs-lookup"><span data-stu-id="f1f9c-135">In more advacned scenarios, it might make more sense to move your dynamic data into a structured [Configuration Data](configData.md).</span></span>

<span data-ttu-id="f1f9c-136">Этот пример конфигурации теперь принимает динамический `$ServiceName`, но если тип не задан, компиляция приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-136">The example Configuration now takes a dynamic `$ServiceName`, but if one is not specified, compiling results in an error.</span></span> <span data-ttu-id="f1f9c-137">Можно добавить значение по умолчанию, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-137">You could add a default value like this example.</span></span>

```powershell
[String]
$ServiceName="Spooler"
```

<span data-ttu-id="f1f9c-138">В этом экземпляре, смысл просто заставить пользователю указать значение для `$ServiceName` параметра.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-138">In this instance though, it makes more sense to simply force the user to specify a value for the `$ServiceName` parameter.</span></span> <span data-ttu-id="f1f9c-139">`parameter` Атрибут позволяет добавлять дополнительные проверки и конвейера, поддерживают параметрам вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-139">The `parameter` attribute allows you to add further validation and pipeline support to your Configuration's parameters.</span></span>

<span data-ttu-id="f1f9c-140">Добавьте над любое объявление параметра `parameter` блок атрибутов, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-140">Above any parameter declaration, add the `parameter` attribute block as in the example below.</span></span>

```powershell
[parameter()]
[String]
$ServiceName
```

<span data-ttu-id="f1f9c-141">Можно указать аргументы для каждого `parameter` атрибут, чтобы управлять различными аспектами определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-141">You can specify arguments to each `parameter` attribute, to control aspects of the defined parameter.</span></span> <span data-ttu-id="f1f9c-142">В нижеследующем примере `$ServiceName` **обязательные** параметра.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-142">The following example makes the `$ServiceName` a **Mandatory** parameter.</span></span>

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

<span data-ttu-id="f1f9c-143">Для `$State` параметра, мы бы хотели запрет на указание значений за пределами предопределенного набора (например, выполнение, остановлен) `ValidationSet*`атрибут будет запрет на указание значений за пределами предопределенного набора (например, выполнение, Остановлен).</span><span class="sxs-lookup"><span data-stu-id="f1f9c-143">For the `$State` parameter, we would like to prevent the user from specifying values outside of a predefined set (like Running, Stopped) the `ValidationSet*`attribute would prevent the user from specifying values outside of a predefined set (like Running, Stopped).</span></span> <span data-ttu-id="f1f9c-144">В следующем примере добавляется `ValidationSet` атрибут `$State` параметра.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-144">The following example adds the `ValidationSet` attribute to the `$State` parameter.</span></span> <span data-ttu-id="f1f9c-145">Так как мы не хотели бы `$State` параметр **обязательные**, нам нужно будет добавить для него значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-145">Since we do not want to make the `$State` parameter **Mandatory**, we will need to add a default value for it.</span></span>

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> <span data-ttu-id="f1f9c-146">Необходимо указать `parameter` атрибут при использовании `validation` атрибута.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-146">You do not need to specify a `parameter` attribute when using a `validation` attribute.</span></span>

<span data-ttu-id="f1f9c-147">Дополнительные сведения о `parameter` и атрибуты проверки в [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f1f9c-147">You can read more about the `parameter` and validation attributes in [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters.md).</span></span>

## <a name="fully-parameterized-configuration"></a><span data-ttu-id="f1f9c-148">Полностью параметризованных конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f9c-148">Fully parameterized Configuration</span></span>

<span data-ttu-id="f1f9c-149">Теперь у нас есть параметризованные конфигурации, которая вынуждает пользователя для указания `-InstanceName`, `-ServiceName`и проверяет `-State` параметра.</span><span class="sxs-lookup"><span data-stu-id="f1f9c-149">We now have a parameterized Configuration that forces the user to specify an `-InstanceName`, `-ServiceName`, and validates the `-State` parameter.</span></span>

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

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f1f9c-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1f9c-150">See also</span></span>

- [<span data-ttu-id="f1f9c-151">Создание справки по конфигурациям DSC</span><span class="sxs-lookup"><span data-stu-id="f1f9c-151">Write help for DSC configurations</span></span>](configHelp.md)
- [<span data-ttu-id="f1f9c-152">Динамические конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f9c-152">Dynamic Configurations</span></span>](flow-control-in-configurations.md)
- [<span data-ttu-id="f1f9c-153">Использовать данные конфигурации в конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1f9c-153">Use Configuration Data in your Configurations</span></span>](configData.md)
- [<span data-ttu-id="f1f9c-154">Отдельные конфигурации данных и данных среды</span><span class="sxs-lookup"><span data-stu-id="f1f9c-154">Separate configuration and environment data</span></span>](separatingEnvData.md)
