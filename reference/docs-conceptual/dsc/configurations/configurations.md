---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Конфигурации DSC
description: Конфигурации DSC — это сценарии PowerShell, определяющие особый тип функции.
ms.openlocfilehash: e59ad2791055ee3ff0150c342ec621d0228c4fc1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658563"
---
# <a name="dsc-configurations"></a><span data-ttu-id="bde7a-104">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="bde7a-104">DSC Configurations</span></span>

> <span data-ttu-id="bde7a-105">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="bde7a-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="bde7a-106">Конфигурации DSC — это сценарии PowerShell, определяющие особый тип функции.</span><span class="sxs-lookup"><span data-stu-id="bde7a-106">DSC configurations are PowerShell scripts that define a special type of function.</span></span> <span data-ttu-id="bde7a-107">Для определения конфигурации используйте ключевое слово PowerShell **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="bde7a-107">To define a configuration, you use the PowerShell keyword **Configuration** .</span></span>

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

<span data-ttu-id="bde7a-108">Сохраните скрипт в виде файла `.ps1`.</span><span class="sxs-lookup"><span data-stu-id="bde7a-108">Save the script as a `.ps1` file.</span></span>

## <a name="configuration-syntax"></a><span data-ttu-id="bde7a-109">Синтаксис конфигурации</span><span class="sxs-lookup"><span data-stu-id="bde7a-109">Configuration syntax</span></span>

<span data-ttu-id="bde7a-110">Сценарий конфигурации состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="bde7a-110">A configuration script consists of the following parts:</span></span>

- <span data-ttu-id="bde7a-111">Блок **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="bde7a-111">The **Configuration** block.</span></span> <span data-ttu-id="bde7a-112">Это основной блок сценария.</span><span class="sxs-lookup"><span data-stu-id="bde7a-112">This is the outermost script block.</span></span> <span data-ttu-id="bde7a-113">Для его определения необходимо использовать ключевое слово **Configuration** и указать имя.</span><span class="sxs-lookup"><span data-stu-id="bde7a-113">You define it by using the **Configuration** keyword and providing a name.</span></span> <span data-ttu-id="bde7a-114">В этом случае имя конфигурации — MyDscConfiguration.</span><span class="sxs-lookup"><span data-stu-id="bde7a-114">In this case, the name of the configuration is "MyDscConfiguration".</span></span>
- <span data-ttu-id="bde7a-115">Один блок **Node** или несколько.</span><span class="sxs-lookup"><span data-stu-id="bde7a-115">One or more **Node** blocks.</span></span> <span data-ttu-id="bde7a-116">Определяют настраиваемые вами узлы (компьютеры или виртуальные машины).</span><span class="sxs-lookup"><span data-stu-id="bde7a-116">These define the nodes (computers or VMs) that you are configuring.</span></span>
  <span data-ttu-id="bde7a-117">В представленной выше конфигурации присутствует один блок **Node** , соответствующий компьютеру с именем TEST-PC1.</span><span class="sxs-lookup"><span data-stu-id="bde7a-117">In the above configuration, there is one **Node** block that targets a computer named "TEST-PC1".</span></span>
  <span data-ttu-id="bde7a-118">Блок Node может принимать несколько имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bde7a-118">The Node block can accept multiple computer names.</span></span>
- <span data-ttu-id="bde7a-119">Один блок ресурсов или несколько.</span><span class="sxs-lookup"><span data-stu-id="bde7a-119">One or more resource blocks.</span></span> <span data-ttu-id="bde7a-120">В этих блоках конфигурация определяет свойства настраиваемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bde7a-120">This is where the configuration sets the properties for the resources that it is configuring.</span></span> <span data-ttu-id="bde7a-121">В данном случае используются два блока ресурсов, каждый из которых вызывает ресурс WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="bde7a-121">In this case, there are two resource blocks, each of which call the "WindowsFeature" resource.</span></span>

<span data-ttu-id="bde7a-122">В блоке **Configuration** можно делать все то же самое, что и в функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bde7a-122">Within a **Configuration** block, you can do anything that you normally could in a PowerShell function.</span></span> <span data-ttu-id="bde7a-123">Например, в предыдущем примере вместо того, чтобы прописывать имя целевого компьютера конфигурации в коде, можно добавить в имя узла соответствующий параметр:</span><span class="sxs-lookup"><span data-stu-id="bde7a-123">For example, in the previous example, if you didn't want to hard code the name of the target computer in the configuration, you could add a parameter for the node name:</span></span>

<span data-ttu-id="bde7a-124">В этом примере вы указываете имя узла, передавая его как параметр **ComputerName** при компиляции конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bde7a-124">In this example, you specify the name of the node by passing it as the **ComputerName** parameter when you compile the configuration.</span></span> <span data-ttu-id="bde7a-125">По умолчанию используется имя localhost.</span><span class="sxs-lookup"><span data-stu-id="bde7a-125">The name defaults to "localhost".</span></span>

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

<span data-ttu-id="bde7a-126">Блок **Node** также может принимать несколько имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bde7a-126">The **Node** block can also accept multiple computer names.</span></span> <span data-ttu-id="bde7a-127">В приведенном выше примере вы можете использовать параметр `-ComputerName` или передать разделенный запятыми список компьютеров непосредственно в блок **Node** .</span><span class="sxs-lookup"><span data-stu-id="bde7a-127">In the above example, you can either use the `-ComputerName` parameter, or pass a comma-separated list of computers directly to the **Node** block.</span></span>

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

<span data-ttu-id="bde7a-128">При указании списка компьютеров для блока **Node** из конфигурации необходимо использовать нотацию массива.</span><span class="sxs-lookup"><span data-stu-id="bde7a-128">When specifying a list of computers to the **Node** block, from within a Configuration, you need to use array-notation.</span></span>

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

## <a name="compiling-the-configuration"></a><span data-ttu-id="bde7a-129">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="bde7a-129">Compiling the configuration</span></span>

<span data-ttu-id="bde7a-130">Прежде чем активировать конфигурацию, необходимо скомпилировать ее в MOF-документ.</span><span class="sxs-lookup"><span data-stu-id="bde7a-130">Before you can enact a configuration, you have to compile it into a MOF document.</span></span> <span data-ttu-id="bde7a-131">Для этого нужно вызвать конфигурацию так же, как вы вызывали функцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bde7a-131">You do this by calling the configuration like you would call a PowerShell function.</span></span> <span data-ttu-id="bde7a-132">Последняя строка примера, содержащего только имя конфигурации, вызывает конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bde7a-132">The last line of the example containing only the name of the configuration, calls the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="bde7a-133">Для вызова конфигурации функция должна находиться в глобальной области видимости (как и любая другая функция PowerShell).</span><span class="sxs-lookup"><span data-stu-id="bde7a-133">To call a configuration, the function must be in global scope (as with any other PowerShell function).</span></span> <span data-ttu-id="bde7a-134">Для этого нужно либо использовать вызов сценария с точкой, либо выполнить сценарий конфигурации, нажав клавишу F5 или кнопку **Выполнить сценарий** в интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="bde7a-134">You can make this happen either by "dot-sourcing" the script, or by running the configuration script by using F5 or clicking on the **Run Script** button in the ISE.</span></span> <span data-ttu-id="bde7a-135">Чтобы использовать вызов сценария с точкой, выполните команду `. .\myConfig.ps1`, где `myConfig.ps1` — это имя файла сценария, который содержит конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bde7a-135">To dot-source the script, run the command `. .\myConfig.ps1` where `myConfig.ps1` is the name of the script file that contains your configuration.</span></span>

<span data-ttu-id="bde7a-136">При вызове конфигурации она выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bde7a-136">When you call the configuration, it:</span></span>

- <span data-ttu-id="bde7a-137">разрешает все переменные;</span><span class="sxs-lookup"><span data-stu-id="bde7a-137">Resolves all variables</span></span>
- <span data-ttu-id="bde7a-138">создает папку в текущем каталоге с тем же именем, что и у конфигурации;</span><span class="sxs-lookup"><span data-stu-id="bde7a-138">Creates a folder in the current directory with the same name as the configuration.</span></span>
- <span data-ttu-id="bde7a-139">создает файл с именем _имя_узла_ .mof в новой папке, где _имя_узла_  — это имя целевого узла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bde7a-139">Creates a file named _NodeName_ .mof in the new directory, where _NodeName_ is the name of the target node of the configuration.</span></span> <span data-ttu-id="bde7a-140">Если узлов несколько, MOF-файл создается для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="bde7a-140">If there is more than one node, a MOF file will be created for each node.</span></span>

> [!NOTE]
> <span data-ttu-id="bde7a-141">MOF-файл содержит все сведения о конфигурации целевого узла.</span><span class="sxs-lookup"><span data-stu-id="bde7a-141">The MOF file contains all of the configuration information for the target node.</span></span> <span data-ttu-id="bde7a-142">Поэтому его необходимо хранить в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="bde7a-142">Because of this, it's important to keep it secure.</span></span> <span data-ttu-id="bde7a-143">Дополнительные сведения см. в статье [Защита MOF-файла](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="bde7a-143">For more information, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>

<span data-ttu-id="bde7a-144">При компиляции первой приведенной конфигурации создается следующая структура папок:</span><span class="sxs-lookup"><span data-stu-id="bde7a-144">Compiling the first configuration above results in the following folder structure:</span></span>

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

<span data-ttu-id="bde7a-145">Если конфигурация принимает какой-либо параметр, как во втором примере, его необходимо указывать во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="bde7a-145">If the configuration takes a parameter, as in the second example, that has to be provided at compile time.</span></span> <span data-ttu-id="bde7a-146">Вот как это выглядит:</span><span class="sxs-lookup"><span data-stu-id="bde7a-146">Here's how that would look:</span></span>

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

## <a name="using-new-resources-in-your-configuration"></a><span data-ttu-id="bde7a-147">Использование новых ресурсов в конфигурации</span><span class="sxs-lookup"><span data-stu-id="bde7a-147">Using new resources in Your configuration</span></span>

<span data-ttu-id="bde7a-148">Выполняя предыдущие примеры, вы могли заметить предупреждение о том, что используемый ресурс не импортирован.</span><span class="sxs-lookup"><span data-stu-id="bde7a-148">If you ran the previous examples, you might have noticed that you were warned that you were using a resource without explicitly importing it.</span></span> <span data-ttu-id="bde7a-149">Сейчас DSC поставляется с модулем PSDesiredStateConfiguration, в который входят 12 ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bde7a-149">Today, DSC ships with 12 resources as part of the PSDesiredStateConfiguration module.</span></span>

<span data-ttu-id="bde7a-150">Командлет [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) позволяет определить, какие ресурсы установлены в системе и доступны для использования LCM.</span><span class="sxs-lookup"><span data-stu-id="bde7a-150">The cmdlet, [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), can be used to determine what resources are installed on the system and available for use by the LCM.</span></span>
<span data-ttu-id="bde7a-151">После добавления в `$env:PSModulePath` и правильного распознавания командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) эти модули нужно будет загрузить в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bde7a-151">Once these modules have been placed in `$env:PSModulePath` and are properly recognized by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), they still need to be loaded within your configuration.</span></span>

<span data-ttu-id="bde7a-152">**Import-DscResource**  — это динамическое ключевое слово, распознаваемое только в блоке **Configuration** , и оно не является командлетом.</span><span class="sxs-lookup"><span data-stu-id="bde7a-152">**Import-DscResource** is a dynamic keyword that can only be recognized within a **Configuration** block, it is not a cmdlet.</span></span> <span data-ttu-id="bde7a-153">**Import-DscResource** поддерживает два параметра:</span><span class="sxs-lookup"><span data-stu-id="bde7a-153">**Import-DscResource** supports two parameters:</span></span>

- <span data-ttu-id="bde7a-154">Параметр **ModuleName** — рекомендуемый способ применения **Import-DscResource** .</span><span class="sxs-lookup"><span data-stu-id="bde7a-154">**ModuleName** is the recommended way of using **Import-DscResource** .</span></span> <span data-ttu-id="bde7a-155">Он принимает имя модуля, содержащего ресурсы для импорта (а также массив строк с именами модулей).</span><span class="sxs-lookup"><span data-stu-id="bde7a-155">It accepts the name of the module that contains the resources to be imported (as well as a string array of module names).</span></span>
- <span data-ttu-id="bde7a-156">Параметр **Name** — имя импортируемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="bde7a-156">**Name** is the name of the resource to import.</span></span> <span data-ttu-id="bde7a-157">Это не то понятное имя, которое возвращается командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), а имя класса, используемое при определении схемы ресурса (возвращается как параметр **ResourceType** командлетом [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span><span class="sxs-lookup"><span data-stu-id="bde7a-157">This is not the friendly name returned as "Name" by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), but the class name used when defining the resource schema (returned as **ResourceType** by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span></span>

<span data-ttu-id="bde7a-158">Дополнительные сведения об использовании `Import-DSCResource` см. в статье об [использовании Import-DSCResource](import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="bde7a-158">For more information on using `Import-DSCResource`, see [Using Import-DSCResource](import-dscresource.md)</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="bde7a-159">Различия PowerShell версий 4 и 5</span><span class="sxs-lookup"><span data-stu-id="bde7a-159">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="bde7a-160">Из-за существующих различий ресурсы DSC должны храниться в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="bde7a-160">There are differences in where DSC resources need to be stored in PowerShell 4.0.</span></span> <span data-ttu-id="bde7a-161">Дополнительные сведения см. в разделе о [расположении ресурса](import-dscresource.md#resource-location).</span><span class="sxs-lookup"><span data-stu-id="bde7a-161">For more information, see [Resource location](import-dscresource.md#resource-location).</span></span>

## <a name="see-also"></a><span data-ttu-id="bde7a-162">См. также</span><span class="sxs-lookup"><span data-stu-id="bde7a-162">See Also</span></span>

- [<span data-ttu-id="bde7a-163">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="bde7a-163">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="bde7a-164">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="bde7a-164">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="bde7a-165">Настройка локального диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="bde7a-165">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
