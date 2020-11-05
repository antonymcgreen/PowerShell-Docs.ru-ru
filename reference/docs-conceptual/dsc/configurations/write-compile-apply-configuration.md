---
ms.date: 06/22/2020
keywords: dsc,powershell,настройка,служба,установка
title: Создание, компиляция и применение конфигурации
description: В этом упражнении демонстрируется весь процесс создания и применения конфигурации DSC. В следующем примере вы узнаете, как написать и применить очень простую конфигурацию.
ms.openlocfilehash: f173fe0dc6cd73e2b49bb8c44a9ee1a53eab475f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645039"
---
# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="3bdda-105">Создание, компиляция и применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="3bdda-105">Write, Compile, and Apply a Configuration</span></span>

> <span data-ttu-id="3bdda-106">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3bdda-106">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="3bdda-107">В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="3bdda-107">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="3bdda-108">В следующем примере вы узнаете, как написать и применить очень простую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3bdda-108">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="3bdda-109">Конфигурация будет гарантировать, что файл "HelloWorld.txt" существует на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3bdda-109">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span>
<span data-ttu-id="3bdda-110">В случае удаления файла DSC будет создавать его заново при очередном обновлении.</span><span class="sxs-lookup"><span data-stu-id="3bdda-110">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="3bdda-111">См. дополнительные сведения об особенностях работы с DSC в [обзоре платформы Desired State Configuration для разработчиков](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="3bdda-111">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="3bdda-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3bdda-112">Requirements</span></span>

<span data-ttu-id="3bdda-113">Для выполнения этого примера вам понадобится компьютер с PowerShell 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="3bdda-113">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="3bdda-114">Запись конфигурации</span><span class="sxs-lookup"><span data-stu-id="3bdda-114">Write the configuration</span></span>

<span data-ttu-id="3bdda-115">[Конфигурация](configurations.md) DSC — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).</span><span class="sxs-lookup"><span data-stu-id="3bdda-115">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="3bdda-116">В интегрированной среде сценариев PowerShell или другом редакторе PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="3bdda-116">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

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
> <span data-ttu-id="3bdda-117">В более сложных сценариях, когда нужно импортировать несколько модулей, чтобы работать с множеством ресурсов DSC в одной конфигурации, обязательно помещайте каждый модуль в отдельную строку с помощью `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-117">In more advanced scenarios where multiple modules need to be imported so you can work with many DSC Resources in the same configuration, make sure to put each module in a separate line using `Import-DscResource`.</span></span> <span data-ttu-id="3bdda-118">Такое поведение проще поддерживать в системе управления версиями. Оно требуется при работе с DSC в Azure State Configuration.</span><span class="sxs-lookup"><span data-stu-id="3bdda-118">This is easier to maintain in source control and required when working with DSC in Azure State Configuration.</span></span>
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

<span data-ttu-id="3bdda-119">Сохраните файл как "HelloWorld.ps1".</span><span class="sxs-lookup"><span data-stu-id="3bdda-119">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="3bdda-120">Определение конфигурации аналогично определению функции.</span><span class="sxs-lookup"><span data-stu-id="3bdda-120">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="3bdda-121">Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-121">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="3bdda-122">Конфигурация вызывает один элемент [resources](../resources/resources.md), а именно ресурс `File`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-122">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="3bdda-123">Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bdda-123">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="3bdda-124">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="3bdda-124">Compile the configuration</span></span>

<span data-ttu-id="3bdda-125">Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="3bdda-125">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="3bdda-126">Выполнение конфигурации, как и функции, скомпилирует один файл `.mof` для каждого узла, определенного в блоке `Node`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-126">Running the configuration, like a function, will compile one `.mof` file for every Node defined by the `Node` block.</span></span> <span data-ttu-id="3bdda-127">Чтобы запустить конфигурацию, необходимо _ввести по префиксу-точке_ скрипт `HelloWorld.ps1` в текущей области.</span><span class="sxs-lookup"><span data-stu-id="3bdda-127">In order to run the configuration, you need to _dot source_ your `HelloWorld.ps1` script into the current scope.</span></span> <span data-ttu-id="3bdda-128">Дополнительные сведения см. в статье [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="3bdda-128">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="3bdda-129">_Введите по префиксу-точке_ скрипт `HelloWorld.ps1`, указав путь, где вы сохранили его, после `. ` (точка, пробел).</span><span class="sxs-lookup"><span data-stu-id="3bdda-129">_Dot source_ your `HelloWorld.ps1` script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="3bdda-130">Затем можно запустить конфигурацию, вызвав ее как функцию.</span><span class="sxs-lookup"><span data-stu-id="3bdda-130">You may then, run your configuration by calling it like a function.</span></span> <span data-ttu-id="3bdda-131">Можно также вызвать функцию конфигурации в нижней части скрипта, чтобы не нужно было использовать префикс-точку.</span><span class="sxs-lookup"><span data-stu-id="3bdda-131">You could also invoke the configuration function at the bottom of the script so that you don't need to dot-source.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

<span data-ttu-id="3bdda-132">Будут созданы следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="3bdda-132">This generates the following output:</span></span>

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="3bdda-133">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="3bdda-133">Apply the configuration</span></span>

<span data-ttu-id="3bdda-134">Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="3bdda-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="3bdda-135">Командлет `Start-DscConfiguration` сообщает [локальному диспетчеру конфигураций (LCM)](../managing-nodes/metaConfig.md) (ядру DSC) о необходимости применить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3bdda-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="3bdda-136">LCM вызывает ресурсы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bdda-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="3bdda-137">Используйте приведенный ниже код для выполнения командлета `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-137">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="3bdda-138">Укажите путь к каталогу, где хранится `localhost.mof`, в параметре **Path**.</span><span class="sxs-lookup"><span data-stu-id="3bdda-138">Specify the directory path where your `localhost.mof` is stored to the **Path** parameter.</span></span> <span data-ttu-id="3bdda-139">Командлет `Start-DSCConfiguration` просматривает каталог, указанный для любых файлов вида `<computername>.mof`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-139">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any `<computername>.mof` files.</span></span> <span data-ttu-id="3bdda-140">Командлет `Start-DSCConfiguration` пытается применить каждый файл `.mof`, который найдет, к `computername`, указанному в имени файла (localhost, server01, dc-02 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3bdda-140">The `Start-DSCConfiguration` cmdlet attempts to apply each `.mof` file it finds to the `computername` specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="3bdda-141">Если параметр `-Wait` не указан, `Start-DSCConfiguration` создает фоновое задание для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="3bdda-141">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="3bdda-142">Указание параметра `-Verbose` позволяет наблюдать **подробные** результаты операции.</span><span class="sxs-lookup"><span data-stu-id="3bdda-142">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="3bdda-143">И `-Wait`, и `-Verbose` — необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="3bdda-143">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="3bdda-144">Тестирование конфигурации</span><span class="sxs-lookup"><span data-stu-id="3bdda-144">Test the configuration</span></span>

<span data-ttu-id="3bdda-145">Когда командлет `Start-DSCConfiguration` будет завершен, вы увидите файл `HelloWorld.txt` в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="3bdda-145">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a `HelloWorld.txt` file in the location you specified.</span></span> <span data-ttu-id="3bdda-146">Можно проверить его содержимое с помощью командлета [Get-Content](/powershell/module/microsoft.powershell.management/get-content).</span><span class="sxs-lookup"><span data-stu-id="3bdda-146">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="3bdda-147">Вы также можете _протестировать_ текущее состояние с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3bdda-147">You can also _test_ the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="3bdda-148">Результат должен быть равен `True`, если узел в настоящее время соответствует применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bdda-148">The output should be `True` if the Node is currently compliant with the applied Configuration.</span></span>

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

## <a name="re-applying-the-configuration"></a><span data-ttu-id="3bdda-149">Повторное применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="3bdda-149">Re-applying the configuration</span></span>

<span data-ttu-id="3bdda-150">Чтобы повторно применить конфигурацию, можно удалить текстовый файл, созданный вашей конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3bdda-150">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="3bdda-151">Затем используйте командлет `Start-DSCConfiguration` с параметром `-UseExisting`.</span><span class="sxs-lookup"><span data-stu-id="3bdda-151">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="3bdda-152">Параметр `-UseExisting` указывает `Start-DSCConfiguration` повторно применить файл "current.mof", который представляет последнюю успешно примененную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3bdda-152">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="3bdda-153">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3bdda-153">Next steps</span></span>

- <span data-ttu-id="3bdda-154">См. дополнительные сведения о [конфигурации DSC](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="3bdda-154">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="3bdda-155">См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="3bdda-155">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="3bdda-156">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="3bdda-156">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
