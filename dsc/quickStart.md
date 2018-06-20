---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Краткое руководство по настройке требуемого состояния
ms.openlocfilehash: eb7572f39f7a2710c82f132f42c3502b15c48d0f
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219051"
---
> <span data-ttu-id="8f869-103">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8f869-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="desired-state-configuration-quick-start"></a><span data-ttu-id="8f869-104">Краткое руководство по Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="8f869-104">Desired State Configuration Quick Start</span></span>

<span data-ttu-id="8f869-105">В этом упражнении демонстрируется создание и применение конфигурации, используемой при настройке требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="8f869-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="8f869-106">В нашем примере на сервере будет включен компонент `Web-Server` (IIS), а содержимое простого веб-сайта "Hello World" будет расположено на этом сервере в каталоге `intepub\wwwroot`.</span><span class="sxs-lookup"><span data-stu-id="8f869-106">The example we'll use ensures that a server has the `Web-Server` (IIS) feature enabled, and that the content for a simple "Hello World" website is present in the `intepub\wwwroot` directory of that server.</span></span>

<span data-ttu-id="8f869-107">См. дополнительные сведения об особенностях [настройки требуемого состояния для руководителей](decisionMaker.md).</span><span class="sxs-lookup"><span data-stu-id="8f869-107">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Decision Makers](decisionMaker.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="8f869-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8f869-108">Requirements</span></span>

<span data-ttu-id="8f869-109">Для выполнения этого примера вам понадобится компьютер под управлением Windows Server 2012 или более поздней версии и PowerShell 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8f869-109">To run this example, you will need a computer running Windows Server 2012 or later and PowerShell 4.0 or later.</span></span>

## <a name="write-and-place-the-indexhtm-file"></a><span data-ttu-id="8f869-110">Запись и размещение файла index.htm</span><span class="sxs-lookup"><span data-stu-id="8f869-110">Write and place the index.htm file</span></span>

<span data-ttu-id="8f869-111">Сначала мы создадим файл HTML, который будет использоваться как содержимое веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="8f869-111">First, we'll create the HTML file that we will use as the website content.</span></span>

<span data-ttu-id="8f869-112">В корневой папке создайте папку с именем `test`.</span><span class="sxs-lookup"><span data-stu-id="8f869-112">In your root folder, create a folder named `test`.</span></span>

<span data-ttu-id="8f869-113">В текстовом редакторе введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="8f869-113">In a text editor, type the following text:</span></span>

```html
<head></head>
<body>
<p>Hello World!</p>
</body>
```

<span data-ttu-id="8f869-114">Сохраните текст как файл `index.htm` в ранее созданной папке `test`.</span><span class="sxs-lookup"><span data-stu-id="8f869-114">Save this as `index.htm` in the `test` folder you created earlier.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="8f869-115">Запись конфигурации</span><span class="sxs-lookup"><span data-stu-id="8f869-115">Write the configuration</span></span>

<span data-ttu-id="8f869-116">[Конфигурация DSC](configurations.md) — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).</span><span class="sxs-lookup"><span data-stu-id="8f869-116">A [DSC configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (nodes).</span></span>

<span data-ttu-id="8f869-117">В среде PowerShell ISE введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="8f869-117">In the PowerShell ISE, type the following:</span></span>

```powershell
Configuration WebsiteTest {

    # Import the module that contains the resources we're using.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets this configuration will be applied to.
    Node 'localhost' {

        # The first resource block ensures that the Web-Server (IIS) feature is enabled.
        WindowsFeature WebServer {
            Ensure = "Present"
            Name   = "Web-Server"
        }

        # The second resource block ensures that the website content copied to the website root folder.
        File WebsiteContent {
            Ensure = 'Present'
            SourcePath = 'c:\test\index.htm'
            DestinationPath = 'c:\inetpub\wwwroot'
        }
    }
}
```

<span data-ttu-id="8f869-118">Сохраните файл как `WebsiteTest.ps1`.</span><span class="sxs-lookup"><span data-stu-id="8f869-118">Save the file as `WebsiteTest.ps1`.</span></span>

<span data-ttu-id="8f869-119">Как видно, текст выглядит как функция PowerShell, перед именем которой добавлено ключевое слово **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="8f869-119">You can see that it looks like a PowerShell function, with the addition of the keyword **Configuration** used before the name of the function.</span></span>

<span data-ttu-id="8f869-120">Блок **Node** определяет настраиваемый целевой узел; в нашем примере это `localhost`.</span><span class="sxs-lookup"><span data-stu-id="8f869-120">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="8f869-121">Конфигурация вызывает два [ресурса](resources.md): [WindowsFeature](windowsFeatureResource.md) и [File](fileResource.md).</span><span class="sxs-lookup"><span data-stu-id="8f869-121">The configuration calls two [resources](resources.md), [WindowsFeature](windowsFeatureResource.md) and [File](fileResource.md).</span></span>
<span data-ttu-id="8f869-122">Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8f869-122">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="8f869-123">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="8f869-123">Compile the configuration</span></span>

<span data-ttu-id="8f869-124">Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="8f869-124">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="8f869-125">Для этого запустите конфигурацию как функцию.</span><span class="sxs-lookup"><span data-stu-id="8f869-125">To do this, you run the configuration like a function.</span></span>
<span data-ttu-id="8f869-126">В консоли PowerShell перейдите к папке с сохраненным файлом конфигурации и выполните следующую команду, чтобы скомпилировать конфигурацию в MOF-файл:</span><span class="sxs-lookup"><span data-stu-id="8f869-126">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following commands to compile the configuration into a MOF file:</span></span>

```powershell
. .\WebsiteTest.ps1
WebsiteTest
```

<span data-ttu-id="8f869-127">Будут созданы следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="8f869-127">This generates the following output:</span></span>

```
Directory: C:\ConfigurationTest\WebsiteTest


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

<span data-ttu-id="8f869-128">Первая строка делает функцию конфигурации доступной в консоли.</span><span class="sxs-lookup"><span data-stu-id="8f869-128">The first line makes the configuration function available in the console.</span></span>
<span data-ttu-id="8f869-129">Вторая строка запускает конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8f869-129">The second line runs the configuration.</span></span>
<span data-ttu-id="8f869-130">Результат — создание папки с именем `WebsiteTest`, которая вложена в текущую папку.</span><span class="sxs-lookup"><span data-stu-id="8f869-130">The result is that a new folder, named `WebsiteTest` is created as a subfolder of the current folder.</span></span>
<span data-ttu-id="8f869-131">Папка `WebsiteTest` содержит файл с именем `localhost.mof`.</span><span class="sxs-lookup"><span data-stu-id="8f869-131">The `WebsiteTest` folder contains a file named `localhost.mof`.</span></span>
<span data-ttu-id="8f869-132">Это файл, который затем можно применить к целевому узлу.</span><span class="sxs-lookup"><span data-stu-id="8f869-132">It is this file that can then be applied to the target node.</span></span>

## <a name="apply-the-configuration"></a><span data-ttu-id="8f869-133">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="8f869-133">Apply the configuration</span></span>

<span data-ttu-id="8f869-134">Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8f869-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration) cmdlet.</span></span>

<span data-ttu-id="8f869-135">Этот командлет `Start-DscConfiguration` сообщает [локальному диспетчеру конфигураций (LCM)](metaConfig.md) (ядру DSC) о необходимости применить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8f869-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](metaConfig.md), which is the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="8f869-136">LCM вызывает ресурсы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8f869-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="8f869-137">В консоли PowerShell перейдите к папке с сохраненным файлом конфигурации и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8f869-137">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following command:</span></span>

```powershell
Start-DscConfiguration .\WebsiteTest
```

## <a name="test-the-configuration"></a><span data-ttu-id="8f869-138">Тестирование конфигурации</span><span class="sxs-lookup"><span data-stu-id="8f869-138">Test the configuration</span></span>

<span data-ttu-id="8f869-139">Чтобы проверить применение конфигурации, можно вызвать командлет [Get DscConfigurationStatus](/reference/5.1/PSDesiredStateConfiguration/Get-DscConfigurationStatus).</span><span class="sxs-lookup"><span data-stu-id="8f869-139">You can call the [Get-DscConfigurationStatus](/reference/5.1/PSDesiredStateConfiguration/Get-DscConfigurationStatus) cmdlet to see whether the configuration succeeded.</span></span>

<span data-ttu-id="8f869-140">Также можно проверить результаты непосредственным образом. В нашем примере для этого нужно перейти к `http://localhost/` в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="8f869-140">You can also test the results directly, in this case by browsing to `http://localhost/` in a web browser.</span></span>
<span data-ttu-id="8f869-141">Вы увидите ранее созданную HTML-страницу "Hello World".</span><span class="sxs-lookup"><span data-stu-id="8f869-141">You should see the "Hello World" HTML page you created as the first step in this example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f869-142">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8f869-142">Next steps</span></span>

- <span data-ttu-id="8f869-143">См. дополнительные сведения о [конфигурации DSC](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="8f869-143">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="8f869-144">См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](resources.md).</span><span class="sxs-lookup"><span data-stu-id="8f869-144">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](resources.md).</span></span>
- <span data-ttu-id="8f869-145">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="8f869-145">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>