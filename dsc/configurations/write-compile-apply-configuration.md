---
ms.date: 12/12/2018
keywords: DSC, powershell, службы, конфигурации программы установки
title: Создание, компиляция и применение конфигурации
ms.openlocfilehash: fa4d98fd12202439ba7025fd8af3fa398653ca05
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402347"
---
> <span data-ttu-id="62da7-103">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="62da7-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="62da7-104">Создание, компиляция и применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="62da7-104">Write, Compile, and Apply a Configuration</span></span>

<span data-ttu-id="62da7-105">В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="62da7-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="62da7-106">В следующем примере вы узнаете, как написать и применить очень простой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-106">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="62da7-107">Конфигурация будет убедитесь, что файл «HelloWorld.txt» существует на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="62da7-107">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span> <span data-ttu-id="62da7-108">При удалении файла, DSC будет создать его заново в следующий раз она обновляет.</span><span class="sxs-lookup"><span data-stu-id="62da7-108">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="62da7-109">Общие сведения о DSC и как это работает, см. в разделе [Desired State Configuration Обзор для разработчиков](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="62da7-109">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="62da7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="62da7-110">Requirements</span></span>

<span data-ttu-id="62da7-111">Для выполнения этого примера требуется компьютер под управлением PowerShell 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="62da7-111">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="62da7-112">Запись конфигурации</span><span class="sxs-lookup"><span data-stu-id="62da7-112">Write the configuration</span></span>

<span data-ttu-id="62da7-113">[Конфигурация](configurations.md) DSC — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).</span><span class="sxs-lookup"><span data-stu-id="62da7-113">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="62da7-114">В интегрированной среде Сценариев PowerShell или другой редактор PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="62da7-114">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

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

<span data-ttu-id="62da7-115">Сохраните файл как «HelloWorld.ps1».</span><span class="sxs-lookup"><span data-stu-id="62da7-115">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="62da7-116">Определение конфигурации — как определение функции.</span><span class="sxs-lookup"><span data-stu-id="62da7-116">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="62da7-117">Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.</span><span class="sxs-lookup"><span data-stu-id="62da7-117">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="62da7-118">Конфигурация вызывает один [ресурсы](../resources/resources.md), `File` ресурсов.</span><span class="sxs-lookup"><span data-stu-id="62da7-118">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="62da7-119">Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-119">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="62da7-120">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="62da7-120">Compile the configuration</span></span>

<span data-ttu-id="62da7-121">Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="62da7-121">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="62da7-122">Выполнение конфигурации, как функция, для каждого узла, определенного параметром компиляции один файл «.mof» `Node` блока.</span><span class="sxs-lookup"><span data-stu-id="62da7-122">Running the configuration, like a function, will compile one ".mof" file for every Node defined by the `Node` block.</span></span>
<span data-ttu-id="62da7-123">Чтобы запустить конфигурацию, необходимо *точкой* «HelloWorld.ps1» сценарий в текущей области.</span><span class="sxs-lookup"><span data-stu-id="62da7-123">In order to run the configuration, you need to *dot source* your "HelloWorld.ps1" script into the current scope.</span></span>
<span data-ttu-id="62da7-124">Дополнительные сведения см. в разделе [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="62da7-124">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span></span>

<span data-ttu-id="62da7-125">*Точкой* «HelloWorld.ps1» скрипта, введя в путь, где вы сохранили его, после `. ` (точка, места).</span><span class="sxs-lookup"><span data-stu-id="62da7-125">*Dot source* your "HelloWorld.ps1" script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="62da7-126">Затем можно запустить конфигурацию, вызвав его как функцию.</span><span class="sxs-lookup"><span data-stu-id="62da7-126">You may then, run your configuration by calling it like a Function.</span></span>

```powershell
. C:\Scripts\WebsiteTest.ps1
HelloWolrd
```

<span data-ttu-id="62da7-127">Будут созданы следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="62da7-127">This generates the following output:</span></span>

```output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="62da7-128">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="62da7-128">Apply the configuration</span></span>

<span data-ttu-id="62da7-129">Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="62da7-129">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="62da7-130">`Start-DscConfiguration` Командлет сообщает об [локальный диспетчер конфигураций (LCM)](../managing-nodes/metaConfig.md), подсистемы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-130">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="62da7-131">LCM вызывает ресурсы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-131">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="62da7-132">Используйте приведенный ниже код для выполнения `Start-DSCConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="62da7-132">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="62da7-133">Укажите путь к каталогу, где «localhost.mof» хранятся в `-Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="62da7-133">Specify the directory path where your "localhost.mof" is stored to the `-Path` parameter.</span></span> <span data-ttu-id="62da7-134">`Start-DSCConfiguration` Командлет просматривает каталог, указанный для любых "\<computername\>.mof» файлы.</span><span class="sxs-lookup"><span data-stu-id="62da7-134">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any "\<computername\>.mof" files.</span></span> <span data-ttu-id="62da7-135">`Start-DSCConfiguration` Командлет пытается применить каждой «.mof» файл, найдет к computername, указанный в параметре filename («localhost», «server01», «dc-02", и т.д.).</span><span class="sxs-lookup"><span data-stu-id="62da7-135">The `Start-DSCConfiguration` cmdlet attempts to apply each ".mof" file it finds to the computername specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="62da7-136">Если `-Wait` параметр не указан, `Start-DSCConfiguration` создает фоновое задание для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="62da7-136">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="62da7-137">Указание `-Verbose` позволяет наблюдать **Verbose** результаты операции.</span><span class="sxs-lookup"><span data-stu-id="62da7-137">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="62da7-138">`-Wait`, и `-Verbose` — оба необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="62da7-138">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="62da7-139">Тестирование конфигурации</span><span class="sxs-lookup"><span data-stu-id="62da7-139">Test the configuration</span></span>

<span data-ttu-id="62da7-140">Один раз `Start-DSCConfiguration` командлет будет завершена, вы увидите файл «HelloWorld.txt» в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="62da7-140">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a "HelloWorld.txt" file in the location you specified.</span></span> <span data-ttu-id="62da7-141">Можно проверить содержимое с [Get-Content](/powershell/module/microsoft.powershell.management/get-content) командлета.</span><span class="sxs-lookup"><span data-stu-id="62da7-141">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="62da7-142">Вы также можете *тестирования* текущее состояние с помощью [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="62da7-142">You can also *test* the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="62da7-143">Требуется «True», является ли узел в настоящее время соответствуют применяемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-143">The output should be "True" if the Node is currently compliant with the applied Configuration.</span></span>

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

## <a name="re-applying-the-configuration"></a><span data-ttu-id="62da7-144">Повторное применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="62da7-144">Re-applying the configuration</span></span>

<span data-ttu-id="62da7-145">Чтобы просмотреть конфигурацию применяться еще раз, можно удалить текстовый файл, созданный вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-145">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="62da7-146">Использование `Start-DSCConfiguration` командлет с `-UseExisting` параметра.</span><span class="sxs-lookup"><span data-stu-id="62da7-146">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="62da7-147">`-UseExisting` Указывает `Start-DSCConfiguration` повторно применить файл «current.mof», который представляет наиболее недавно успешно применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62da7-147">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="62da7-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="62da7-148">Next steps</span></span>

- <span data-ttu-id="62da7-149">См. дополнительные сведения о [конфигурации DSC](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="62da7-149">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="62da7-150">См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="62da7-150">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="62da7-151">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="62da7-151">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
