---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Конфигурации DSC
ms.openlocfilehash: d7749ec88f9cca3e29c6b38d61fb73776af7ceb4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954501"
---
# <a name="dsc-configurations"></a><span data-ttu-id="83065-103">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="83065-103">DSC Configurations</span></span>

> <span data-ttu-id="83065-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="83065-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="83065-105">Конфигурации DSC — это сценарии PowerShell, определяющие особый тип функции.</span><span class="sxs-lookup"><span data-stu-id="83065-105">DSC configurations are PowerShell scripts that define a special type of function.</span></span>
<span data-ttu-id="83065-106">Для определения конфигурации используйте ключевое слово PowerShell **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="83065-106">To define a configuration, you use the PowerShell keyword **Configuration**.</span></span>

```powershell
Configuration MyDscConfiguration {
    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = 'Present'
            Name = 'RSAT'
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}
MyDscConfiguration
```

<span data-ttu-id="83065-107">Сохраните скрипт в виде файла `.ps1`.</span><span class="sxs-lookup"><span data-stu-id="83065-107">Save the script as a `.ps1` file.</span></span>

## <a name="configuration-syntax"></a><span data-ttu-id="83065-108">Синтаксис конфигурации</span><span class="sxs-lookup"><span data-stu-id="83065-108">Configuration syntax</span></span>

<span data-ttu-id="83065-109">Сценарий конфигурации состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="83065-109">A configuration script consists of the following parts:</span></span>

- <span data-ttu-id="83065-110">Блок **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="83065-110">The **Configuration** block.</span></span> <span data-ttu-id="83065-111">Это основной блок сценария.</span><span class="sxs-lookup"><span data-stu-id="83065-111">This is the outermost script block.</span></span> <span data-ttu-id="83065-112">Для его определения необходимо использовать ключевое слово **Configuration** и указать имя.</span><span class="sxs-lookup"><span data-stu-id="83065-112">You define it by using the **Configuration** keyword and providing a name.</span></span> <span data-ttu-id="83065-113">В этом случае имя конфигурации — MyDscConfiguration.</span><span class="sxs-lookup"><span data-stu-id="83065-113">In this case, the name of the configuration is "MyDscConfiguration".</span></span>
- <span data-ttu-id="83065-114">Один блок **Node** или несколько.</span><span class="sxs-lookup"><span data-stu-id="83065-114">One or more **Node** blocks.</span></span> <span data-ttu-id="83065-115">Определяют настраиваемые вами узлы (компьютеры или виртуальные машины).</span><span class="sxs-lookup"><span data-stu-id="83065-115">These define the nodes (computers or VMs) that you are configuring.</span></span> <span data-ttu-id="83065-116">В представленной выше конфигурации присутствует один блок **Node**, соответствующий компьютеру с именем TEST-PC1.</span><span class="sxs-lookup"><span data-stu-id="83065-116">In the above configuration, there is one **Node** block that targets a computer named "TEST-PC1".</span></span> <span data-ttu-id="83065-117">Блок Node может принимать несколько имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="83065-117">The Node block can accept multiple computer names.</span></span>
- <span data-ttu-id="83065-118">Один блок ресурсов или несколько.</span><span class="sxs-lookup"><span data-stu-id="83065-118">One or more resource blocks.</span></span> <span data-ttu-id="83065-119">В этих блоках конфигурация определяет свойства настраиваемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="83065-119">This is where the configuration sets the properties for the resources that it is configuring.</span></span> <span data-ttu-id="83065-120">В данном случае используются два блока ресурсов, каждый из которых вызывает ресурс WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="83065-120">In this case, there are two resource blocks, each of which call the "WindowsFeature" resource.</span></span>

<span data-ttu-id="83065-121">В блоке **Configuration** можно делать все то же самое, что и в функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83065-121">Within a **Configuration** block, you can do anything that you normally could in a PowerShell function.</span></span> <span data-ttu-id="83065-122">Например, в предыдущем примере вместо того, чтобы прописывать имя целевого компьютера конфигурации в коде, можно добавить в имя узла соответствующий параметр:</span><span class="sxs-lookup"><span data-stu-id="83065-122">For example, in the previous example, if you didn't want to hard code the name of the target computer in the configuration, you could add a parameter for the node name:</span></span>

<span data-ttu-id="83065-123">В этом примере вы указываете имя узла, передавая его как параметр **ComputerName** при компиляции конфигурации.</span><span class="sxs-lookup"><span data-stu-id="83065-123">In this example, you specify the name of the node by passing it as the **ComputerName** parameter when you compile the configuration.</span></span> <span data-ttu-id="83065-124">По умолчанию используется имя localhost.</span><span class="sxs-lookup"><span data-stu-id="83065-124">The name defaults to "localhost".</span></span>

```powershell
Configuration MyDscConfiguration
{
    param
    (
        [string[]]$ComputerName='localhost'
    )

    Node $ComputerName
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

<span data-ttu-id="83065-125">Блок **Node** также может принимать несколько имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="83065-125">The **Node** block can also accept multiple computer names.</span></span> <span data-ttu-id="83065-126">В приведенном выше примере вы можете использовать параметр `-ComputerName` или передать разделенный запятыми список компьютеров непосредственно в блок **Node**.</span><span class="sxs-lookup"><span data-stu-id="83065-126">In the above example, you can either use the `-ComputerName` parameter, or pass a comma-separated list of computers directly to the **Node** block.</span></span>

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

<span data-ttu-id="83065-127">При указании списка компьютеров для блока **Node** из конфигурации необходимо использовать нотацию массива.</span><span class="sxs-lookup"><span data-stu-id="83065-127">When specifying a list of computers to the **Node** block, from within a Configuration, you need to use array-notation.</span></span>

```powershell
Configuration MyDscConfiguration
{
    Node @('localhost', 'Server01')
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

## <a name="compiling-the-configuration"></a><span data-ttu-id="83065-128">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="83065-128">Compiling the configuration</span></span>

<span data-ttu-id="83065-129">Прежде чем активировать конфигурацию, необходимо скомпилировать ее в MOF-документ.</span><span class="sxs-lookup"><span data-stu-id="83065-129">Before you can enact a configuration, you have to compile it into a MOF document.</span></span>
<span data-ttu-id="83065-130">Для этого нужно вызвать конфигурацию так же, как вы вызывали функцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83065-130">You do this by calling the configuration like you would call a PowerShell function.</span></span>
<span data-ttu-id="83065-131">Последняя строка примера, содержащего только имя конфигурации, вызывает конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="83065-131">The last line of the example containing only the name of the configuration, calls the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="83065-132">Для вызова конфигурации функция должна находиться в глобальной области видимости (как и любая другая функция PowerShell).</span><span class="sxs-lookup"><span data-stu-id="83065-132">To call a configuration, the function must be in global scope (as with any other PowerShell function).</span></span>
> <span data-ttu-id="83065-133">Для этого нужно либо использовать вызов сценария с точкой, либо выполнить сценарий конфигурации, нажав клавишу F5 или кнопку **Выполнить сценарий** в интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="83065-133">You can make this happen either by "dot-sourcing" the script, or by running the configuration script by using F5 or clicking on the **Run Script** button in the ISE.</span></span>
> <span data-ttu-id="83065-134">Чтобы использовать вызов сценария с точкой, выполните команду `. .\myConfig.ps1`, где `myConfig.ps1` — это имя файла сценария, который содержит конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="83065-134">To dot-source the script, run the command `. .\myConfig.ps1` where `myConfig.ps1` is the name of the script file that contains your configuration.</span></span>

<span data-ttu-id="83065-135">При вызове конфигурации она выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="83065-135">When you call the configuration, it:</span></span>

- <span data-ttu-id="83065-136">разрешает все переменные;</span><span class="sxs-lookup"><span data-stu-id="83065-136">Resolves all variables</span></span>
- <span data-ttu-id="83065-137">создает папку в текущем каталоге с тем же именем, что и у конфигурации;</span><span class="sxs-lookup"><span data-stu-id="83065-137">Creates a folder in the current directory with the same name as the configuration.</span></span>
- <span data-ttu-id="83065-138">создает файл с именем _имя_узла_.mof в новой папке, где _имя_узла_ — это имя целевого узла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="83065-138">Creates a file named _NodeName_.mof in the new directory, where _NodeName_ is the name of the target node of the configuration.</span></span>
  <span data-ttu-id="83065-139">Если узлов несколько, MOF-файл создается для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="83065-139">If there is more than one node, a MOF file will be created for each node.</span></span>

> [!NOTE]
> <span data-ttu-id="83065-140">MOF-файл содержит все сведения о конфигурации целевого узла.</span><span class="sxs-lookup"><span data-stu-id="83065-140">The MOF file contains all of the configuration information for the target node.</span></span> <span data-ttu-id="83065-141">Поэтому его необходимо хранить в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="83065-141">Because of this, it's important to keep it secure.</span></span>
> <span data-ttu-id="83065-142">Дополнительные сведения см. в статье [Защита MOF-файла](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="83065-142">For more information, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>

<span data-ttu-id="83065-143">При компиляции первой приведенной конфигурации создается следующая структура папок:</span><span class="sxs-lookup"><span data-stu-id="83065-143">Compiling the first configuration above results in the following folder structure:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 localhost.mof
```

<span data-ttu-id="83065-144">Если конфигурация принимает какой-либо параметр, как во втором примере, его необходимо указывать во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="83065-144">If the configuration takes a parameter, as in the second example, that has to be provided at compile time.</span></span> <span data-ttu-id="83065-145">Вот как это выглядит:</span><span class="sxs-lookup"><span data-stu-id="83065-145">Here's how that would look:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration -ComputerName 'MyTestNode'
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 MyTestNode.mof
```

## <a name="using-new-resources-in-your-configuration"></a><span data-ttu-id="83065-146">Использование новых ресурсов в конфигурации</span><span class="sxs-lookup"><span data-stu-id="83065-146">Using new resources in Your configuration</span></span>

<span data-ttu-id="83065-147">Выполняя предыдущие примеры, вы могли заметить предупреждение о том, что используемый ресурс не импортирован.</span><span class="sxs-lookup"><span data-stu-id="83065-147">If you ran the previous examples, you might have noticed that you were warned that you were using a resource without explicitly importing it.</span></span>
<span data-ttu-id="83065-148">Сейчас DSC поставляется с модулем PSDesiredStateConfiguration, в который входят 12 ресурсов.</span><span class="sxs-lookup"><span data-stu-id="83065-148">Today, DSC ships with 12 resources as part of the PSDesiredStateConfiguration module.</span></span>

<span data-ttu-id="83065-149">Командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) позволяет определить, какие ресурсы установлены в системе и доступны для использования LCM.</span><span class="sxs-lookup"><span data-stu-id="83065-149">The cmdlet, [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), can be used to determine what resources are installed on the system and available for use by the LCM.</span></span>
<span data-ttu-id="83065-150">После добавления в `$env:PSModulePath` и правильного распознавания командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) эти модули нужно будет загрузить в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="83065-150">Once these modules have been placed in `$env:PSModulePath` and are properly recognized by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), they still need to be loaded within your configuration.</span></span>

<span data-ttu-id="83065-151">**Import-DscResource** — это динамическое ключевое слово, распознаваемое только в блоке **Configuration**, и оно не является командлетом.</span><span class="sxs-lookup"><span data-stu-id="83065-151">**Import-DscResource** is a dynamic keyword that can only be recognized within a **Configuration** block, it is not a cmdlet.</span></span>
<span data-ttu-id="83065-152">**Import-DscResource** поддерживает два параметра:</span><span class="sxs-lookup"><span data-stu-id="83065-152">**Import-DscResource** supports two parameters:</span></span>

- <span data-ttu-id="83065-153">Параметр **ModuleName** — рекомендуемый способ применения **Import-DscResource**.</span><span class="sxs-lookup"><span data-stu-id="83065-153">**ModuleName** is the recommended way of using **Import-DscResource**.</span></span> <span data-ttu-id="83065-154">Он принимает имя модуля, содержащего ресурсы для импорта (а также массив строк с именами модулей).</span><span class="sxs-lookup"><span data-stu-id="83065-154">It accepts the name of the module that contains the resources to be imported (as well as a string array of module names).</span></span>
- <span data-ttu-id="83065-155">Параметр **Name** — имя импортируемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="83065-155">**Name** is the name of the resource to import.</span></span> <span data-ttu-id="83065-156">Это не то понятное имя, которое возвращается командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), а имя класса, используемое при определении схемы ресурса (возвращается как параметр **ResourceType** командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span><span class="sxs-lookup"><span data-stu-id="83065-156">This is not the friendly name returned as "Name" by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), but the class name used when defining the resource schema (returned as **ResourceType** by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span></span>

<span data-ttu-id="83065-157">Дополнительные сведения об использовании `Import-DSCResource` см. в статье об [использовании Import-DSCResource](import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="83065-157">For more information on using `Import-DSCResource`, see [Using Import-DSCResource](import-dscresource.md)</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="83065-158">Различия PowerShell версий 4 и 5</span><span class="sxs-lookup"><span data-stu-id="83065-158">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="83065-159">Из-за существующих различий ресурсы DSC должны храниться в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="83065-159">There are differences in where DSC resources need to be stored in PowerShell 4.0.</span></span> <span data-ttu-id="83065-160">Дополнительные сведения см. в разделе о [расположении ресурса](import-dscresource.md#resource-location).</span><span class="sxs-lookup"><span data-stu-id="83065-160">For more information, see [Resource location](import-dscresource.md#resource-location).</span></span>

## <a name="see-also"></a><span data-ttu-id="83065-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="83065-161">See Also</span></span>

- [<span data-ttu-id="83065-162">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="83065-162">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="83065-163">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="83065-163">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="83065-164">Настройка локального диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="83065-164">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
