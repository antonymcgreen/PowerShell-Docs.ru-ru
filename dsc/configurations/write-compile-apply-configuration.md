---
ms.date: 12/12/2018
keywords: dsc,powershell,настройка,служба,установка
title: Создание, компиляция и применение конфигурации
ms.openlocfilehash: c884af9d92ac375457d6eb75d815ae9a9159e273
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795425"
---
> <span data-ttu-id="7847e-103">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="7847e-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="7847e-104">Создание, компиляция и применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="7847e-104">Write, Compile, and Apply a Configuration</span></span>

<span data-ttu-id="7847e-105">В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="7847e-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="7847e-106">В следующем примере вы узнаете, как написать и применить очень простую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7847e-106">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="7847e-107">Конфигурация будет гарантировать, что файл "HelloWorld.txt" существует на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7847e-107">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span> <span data-ttu-id="7847e-108">В случае удаления файла DSC будет создавать его заново при очередном обновлении.</span><span class="sxs-lookup"><span data-stu-id="7847e-108">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="7847e-109">См. дополнительные сведения об особенностях работы с DSC в [обзоре платформы Desired State Configuration для разработчиков](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="7847e-109">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="7847e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7847e-110">Requirements</span></span>

<span data-ttu-id="7847e-111">Для выполнения этого примера вам понадобится компьютер с PowerShell 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7847e-111">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="7847e-112">Запись конфигурации</span><span class="sxs-lookup"><span data-stu-id="7847e-112">Write the configuration</span></span>

<span data-ttu-id="7847e-113">[Конфигурация](configurations.md) DSC — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).</span><span class="sxs-lookup"><span data-stu-id="7847e-113">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="7847e-114">В интегрированной среде сценариев PowerShell или другом редакторе PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="7847e-114">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

<span data-ttu-id="7847e-115">Сохраните файл как "HelloWorld.ps1".</span><span class="sxs-lookup"><span data-stu-id="7847e-115">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="7847e-116">Определение конфигурации аналогично определению функции.</span><span class="sxs-lookup"><span data-stu-id="7847e-116">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="7847e-117">Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.</span><span class="sxs-lookup"><span data-stu-id="7847e-117">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="7847e-118">Конфигурация вызывает один элемент [resources](../resources/resources.md), а именно ресурс `File`.</span><span class="sxs-lookup"><span data-stu-id="7847e-118">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="7847e-119">Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7847e-119">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="7847e-120">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="7847e-120">Compile the configuration</span></span>

<span data-ttu-id="7847e-121">Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="7847e-121">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="7847e-122">Выполнение конфигурации, как и функции, скомпилирует один MOF-файл для каждого узла, определенного в блоке `Node`.</span><span class="sxs-lookup"><span data-stu-id="7847e-122">Running the configuration, like a function, will compile one ".mof" file for every Node defined by the `Node` block.</span></span>
<span data-ttu-id="7847e-123">Чтобы запустить конфигурацию, необходимо *ввести по префиксу-точке* скрипт "HelloWorld.ps1" в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7847e-123">In order to run the configuration, you need to *dot source* your "HelloWorld.ps1" script into the current scope.</span></span>
<span data-ttu-id="7847e-124">Дополнительные сведения см. в статье [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="7847e-124">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span></span>

<span data-ttu-id="7847e-125"><!-- markdownlint-disable MD038 -->
*Введите по префиксу-точке* скрипт "HelloWorld.ps1", указав путь, где вы сохранили его, после `. ` (точка, пробел).</span><span class="sxs-lookup"><span data-stu-id="7847e-125"><!-- markdownlint-disable MD038 -->
*Dot source* your "HelloWorld.ps1" script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="7847e-126">Затем можно запустить конфигурацию, вызвав ее как функцию.</span><span class="sxs-lookup"><span data-stu-id="7847e-126">You may then, run your configuration by calling it like a Function.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\WebsiteTest.ps1
HelloWolrd
```

<span data-ttu-id="7847e-127">Будут созданы следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="7847e-127">This generates the following output:</span></span>

```output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="7847e-128">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="7847e-128">Apply the configuration</span></span>

<span data-ttu-id="7847e-129">Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="7847e-129">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="7847e-130">Командлет `Start-DscConfiguration` сообщает [локальному диспетчеру конфигураций (LCM)](../managing-nodes/metaConfig.md) (ядру DSC) о необходимости применить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7847e-130">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="7847e-131">LCM вызывает ресурсы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7847e-131">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="7847e-132">Используйте приведенный ниже код для выполнения командлета `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="7847e-132">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="7847e-133">Укажите путь к каталогу, где хранится "localhost.mof", в параметре `-Path`.</span><span class="sxs-lookup"><span data-stu-id="7847e-133">Specify the directory path where your "localhost.mof" is stored to the `-Path` parameter.</span></span> <span data-ttu-id="7847e-134">Командлет `Start-DSCConfiguration` просматривает каталог, указанный для любых файлов вида "\<имя компьютера\>.mof".</span><span class="sxs-lookup"><span data-stu-id="7847e-134">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any "\<computername\>.mof" files.</span></span> <span data-ttu-id="7847e-135">Командлет `Start-DSCConfiguration` пытается применить каждый MOF-файл, который найдет, к компьютеру, указанному в имени файла ("localhost", "server01", "dc-02" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="7847e-135">The `Start-DSCConfiguration` cmdlet attempts to apply each ".mof" file it finds to the computername specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="7847e-136">Если параметр `-Wait` не указан, `Start-DSCConfiguration` создает фоновое задание для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="7847e-136">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="7847e-137">Указание параметра `-Verbose` позволяет наблюдать **подробные** результаты операции.</span><span class="sxs-lookup"><span data-stu-id="7847e-137">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="7847e-138">И `-Wait`, и `-Verbose` — необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="7847e-138">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="7847e-139">Тестирование конфигурации</span><span class="sxs-lookup"><span data-stu-id="7847e-139">Test the configuration</span></span>

<span data-ttu-id="7847e-140">Когда командлет `Start-DSCConfiguration` будет завершен, вы увидите файл "HelloWorld.txt" в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="7847e-140">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a "HelloWorld.txt" file in the location you specified.</span></span> <span data-ttu-id="7847e-141">Можно проверить его содержимое с помощью командлета [Get-Content](/powershell/module/microsoft.powershell.management/get-content).</span><span class="sxs-lookup"><span data-stu-id="7847e-141">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="7847e-142">Вы также можете *протестировать* текущее состояние с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7847e-142">You can also *test* the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="7847e-143">Результат должен быть равен "True", если узел в настоящее время соответствует применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7847e-143">The output should be "True" if the Node is currently compliant with the applied Configuration.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a><span data-ttu-id="7847e-144">Повторное применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="7847e-144">Re-applying the configuration</span></span>

<span data-ttu-id="7847e-145">Чтобы повторно применить конфигурацию, можно удалить текстовый файл, созданный вашей конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="7847e-145">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="7847e-146">Затем используйте командлет `Start-DSCConfiguration` с параметром `-UseExisting`.</span><span class="sxs-lookup"><span data-stu-id="7847e-146">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="7847e-147">Параметр `-UseExisting` указывает `Start-DSCConfiguration` повторно применить файл "current.mof", который представляет последнюю успешно примененную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7847e-147">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="7847e-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7847e-148">Next steps</span></span>

- <span data-ttu-id="7847e-149">См. дополнительные сведения о [конфигурации DSC](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="7847e-149">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="7847e-150">См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="7847e-150">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="7847e-151">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="7847e-151">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
