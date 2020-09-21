---
ms.date: 06/22/2020
keywords: dsc,powershell,настройка,служба,установка
title: Создание, компиляция и применение конфигурации
ms.openlocfilehash: 9acb2db882795d7150326fadb2964deb1105b2cc
ms.sourcegitcommit: 7eea0885dd7ac90ab36e5664501438a292217f7f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85295681"
---
# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="0992c-103">Создание, компиляция и применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="0992c-103">Write, Compile, and Apply a Configuration</span></span>

> <span data-ttu-id="0992c-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0992c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="0992c-105">В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="0992c-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="0992c-106">В следующем примере вы узнаете, как написать и применить очень простую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0992c-106">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="0992c-107">Конфигурация будет гарантировать, что файл "HelloWorld.txt" существует на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0992c-107">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span>
<span data-ttu-id="0992c-108">В случае удаления файла DSC будет создавать его заново при очередном обновлении.</span><span class="sxs-lookup"><span data-stu-id="0992c-108">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="0992c-109">См. дополнительные сведения об особенностях работы с DSC в [обзоре платформы Desired State Configuration для разработчиков](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="0992c-109">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="0992c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0992c-110">Requirements</span></span>

<span data-ttu-id="0992c-111">Для выполнения этого примера вам понадобится компьютер с PowerShell 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="0992c-111">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="0992c-112">Запись конфигурации</span><span class="sxs-lookup"><span data-stu-id="0992c-112">Write the configuration</span></span>

<span data-ttu-id="0992c-113">[Конфигурация](configurations.md) DSC — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).</span><span class="sxs-lookup"><span data-stu-id="0992c-113">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="0992c-114">В интегрированной среде сценариев PowerShell или другом редакторе PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="0992c-114">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when
    # this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a
        # source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="0992c-115">В более сложных сценариях, когда нужно импортировать несколько модулей, чтобы работать с множеством ресурсов DSC в одной конфигурации, обязательно помещайте каждый модуль в отдельную строку с помощью `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="0992c-115">In more advanced scenarios where multiple modules need to be imported so you can work with many DSC Resources in the same configuration, make sure to put each module in a separate line using `Import-DscResource`.</span></span> <span data-ttu-id="0992c-116">Такое поведение проще поддерживать в системе управления версиями. Оно требуется при работе с DSC в Azure State Configuration.</span><span class="sxs-lookup"><span data-stu-id="0992c-116">This is easier to maintain in source control and required when working with DSC in Azure State Configuration.</span></span>
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

<span data-ttu-id="0992c-117">Сохраните файл как "HelloWorld.ps1".</span><span class="sxs-lookup"><span data-stu-id="0992c-117">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="0992c-118">Определение конфигурации аналогично определению функции.</span><span class="sxs-lookup"><span data-stu-id="0992c-118">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="0992c-119">Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.</span><span class="sxs-lookup"><span data-stu-id="0992c-119">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="0992c-120">Конфигурация вызывает один элемент [resources](../resources/resources.md), а именно ресурс `File`.</span><span class="sxs-lookup"><span data-stu-id="0992c-120">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="0992c-121">Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0992c-121">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="0992c-122">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="0992c-122">Compile the configuration</span></span>

<span data-ttu-id="0992c-123">Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="0992c-123">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="0992c-124">Выполнение конфигурации, как и функции, скомпилирует один файл `.mof` для каждого узла, определенного в блоке `Node`.</span><span class="sxs-lookup"><span data-stu-id="0992c-124">Running the configuration, like a function, will compile one `.mof` file for every Node defined by the `Node` block.</span></span> <span data-ttu-id="0992c-125">Чтобы запустить конфигурацию, необходимо _ввести по префиксу-точке_ скрипт `HelloWorld.ps1` в текущей области.</span><span class="sxs-lookup"><span data-stu-id="0992c-125">In order to run the configuration, you need to _dot source_ your `HelloWorld.ps1` script into the current scope.</span></span> <span data-ttu-id="0992c-126">Дополнительные сведения см. в статье [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="0992c-126">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="0992c-127">_Введите по префиксу-точке_ скрипт `HelloWorld.ps1`, указав путь, где вы сохранили его, после `. ` (точка, пробел).</span><span class="sxs-lookup"><span data-stu-id="0992c-127">_Dot source_ your `HelloWorld.ps1` script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="0992c-128">Затем можно запустить конфигурацию, вызвав ее как функцию.</span><span class="sxs-lookup"><span data-stu-id="0992c-128">You may then, run your configuration by calling it like a function.</span></span> <span data-ttu-id="0992c-129">Можно также вызвать функцию конфигурации в нижней части скрипта, чтобы не нужно было использовать префикс-точку.</span><span class="sxs-lookup"><span data-stu-id="0992c-129">You could also invoke the configuration function at the bottom of the script so that you don't need to dot-source.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

<span data-ttu-id="0992c-130">Будут созданы следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="0992c-130">This generates the following output:</span></span>

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="0992c-131">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="0992c-131">Apply the configuration</span></span>

<span data-ttu-id="0992c-132">Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="0992c-132">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="0992c-133">Командлет `Start-DscConfiguration` сообщает [локальному диспетчеру конфигураций (LCM)](../managing-nodes/metaConfig.md) (ядру DSC) о необходимости применить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0992c-133">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="0992c-134">LCM вызывает ресурсы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0992c-134">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="0992c-135">Используйте приведенный ниже код для выполнения командлета `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="0992c-135">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="0992c-136">Укажите путь к каталогу, где хранится `localhost.mof`, в параметре **Path**.</span><span class="sxs-lookup"><span data-stu-id="0992c-136">Specify the directory path where your `localhost.mof` is stored to the **Path** parameter.</span></span> <span data-ttu-id="0992c-137">Командлет `Start-DSCConfiguration` просматривает каталог, указанный для любых файлов вида `<computername>.mof`.</span><span class="sxs-lookup"><span data-stu-id="0992c-137">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any `<computername>.mof` files.</span></span> <span data-ttu-id="0992c-138">Командлет `Start-DSCConfiguration` пытается применить каждый файл `.mof`, который найдет, к `computername`, указанному в имени файла (localhost, server01, dc-02 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="0992c-138">The `Start-DSCConfiguration` cmdlet attempts to apply each `.mof` file it finds to the `computername` specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="0992c-139">Если параметр `-Wait` не указан, `Start-DSCConfiguration` создает фоновое задание для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="0992c-139">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="0992c-140">Указание параметра `-Verbose` позволяет наблюдать **подробные** результаты операции.</span><span class="sxs-lookup"><span data-stu-id="0992c-140">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="0992c-141">И `-Wait`, и `-Verbose` — необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="0992c-141">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="0992c-142">Тестирование конфигурации</span><span class="sxs-lookup"><span data-stu-id="0992c-142">Test the configuration</span></span>

<span data-ttu-id="0992c-143">Когда командлет `Start-DSCConfiguration` будет завершен, вы увидите файл `HelloWorld.txt` в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="0992c-143">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a `HelloWorld.txt` file in the location you specified.</span></span> <span data-ttu-id="0992c-144">Можно проверить его содержимое с помощью командлета [Get-Content](/powershell/module/microsoft.powershell.management/get-content).</span><span class="sxs-lookup"><span data-stu-id="0992c-144">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="0992c-145">Вы также можете _протестировать_ текущее состояние с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0992c-145">You can also _test_ the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="0992c-146">Результат должен быть равен `True`, если узел в настоящее время соответствует применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0992c-146">The output should be `True` if the Node is currently compliant with the applied Configuration.</span></span>

```powershell
Test-DSCConfiguration
```

```Output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```Output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a><span data-ttu-id="0992c-147">Повторное применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="0992c-147">Re-applying the configuration</span></span>

<span data-ttu-id="0992c-148">Чтобы повторно применить конфигурацию, можно удалить текстовый файл, созданный вашей конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="0992c-148">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="0992c-149">Затем используйте командлет `Start-DSCConfiguration` с параметром `-UseExisting`.</span><span class="sxs-lookup"><span data-stu-id="0992c-149">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="0992c-150">Параметр `-UseExisting` указывает `Start-DSCConfiguration` повторно применить файл "current.mof", который представляет последнюю успешно примененную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0992c-150">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="0992c-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0992c-151">Next steps</span></span>

- <span data-ttu-id="0992c-152">См. дополнительные сведения о [конфигурации DSC](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="0992c-152">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="0992c-153">См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="0992c-153">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="0992c-154">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="0992c-154">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
