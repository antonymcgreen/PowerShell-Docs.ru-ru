---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Краткое руководство. Создание веб-сайта с использованием DSC
description: В этом кратком руководстве описывается, как создать веб-сайт с помощью конфигурации DSC.
ms.openlocfilehash: ece1ae964bce00a4102de4b13d99d6ee1259117a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650896"
---
# <a name="quickstart---create-a-website-with-desired-state-configuration-dsc"></a><span data-ttu-id="b88c3-104">Краткое руководство. Создание веб-сайта с использованием Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="b88c3-104">Quickstart - Create a website with Desired State Configuration (DSC)</span></span>

> <span data-ttu-id="b88c3-105">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b88c3-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="b88c3-106">В этом упражнении демонстрируется создание и применение конфигурации Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="b88c3-106">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="b88c3-107">В нашем примере на сервере будет включен компонент `Web-Server` (IIS), а содержимое простого веб-сайта "Hello World" будет расположено на этом сервере в каталоге `inetpub\wwwroot`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-107">The example we'll use ensures that a server has the `Web-Server` (IIS) feature enabled, and that the content for a simple "Hello World" website is present in the `inetpub\wwwroot` directory of that server.</span></span>

<span data-ttu-id="b88c3-108">См. дополнительные сведения об особенностях работы с DSC в [обзоре платформы Desired State Configuration для руководителей](../overview/decisionMaker.md).</span><span class="sxs-lookup"><span data-stu-id="b88c3-108">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Decision Makers](../overview/decisionMaker.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="b88c3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b88c3-109">Requirements</span></span>

<span data-ttu-id="b88c3-110">Для выполнения этого примера вам понадобится компьютер под управлением Windows Server 2012 или более поздней версии и PowerShell 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b88c3-110">To run this example, you will need a computer running Windows Server 2012 or later and PowerShell 4.0 or later.</span></span>

## <a name="write-and-place-the-indexhtm-file"></a><span data-ttu-id="b88c3-111">Запись и размещение файла index.htm</span><span class="sxs-lookup"><span data-stu-id="b88c3-111">Write and place the index.htm file</span></span>

<span data-ttu-id="b88c3-112">Сначала мы создадим файл HTML, который будет использоваться как содержимое веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="b88c3-112">First, we'll create the HTML file that we will use as the website content.</span></span>

<span data-ttu-id="b88c3-113">В корневой папке создайте папку с именем `test`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-113">In your root folder, create a folder named `test`.</span></span>

<span data-ttu-id="b88c3-114">В текстовом редакторе введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="b88c3-114">In a text editor, type the following text:</span></span>

```html
<head></head>
<body>
<p>Hello World!</p>
</body>
```

<span data-ttu-id="b88c3-115">Сохраните текст как файл `index.htm` в ранее созданной папке `test`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-115">Save this as `index.htm` in the `test` folder you created earlier.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="b88c3-116">Запись конфигурации</span><span class="sxs-lookup"><span data-stu-id="b88c3-116">Write the configuration</span></span>

<span data-ttu-id="b88c3-117">[Конфигурация DSC](../configurations/configurations.md) — это специальная функция PowerShell, которая определяет способ настройки одного или нескольких целевых компьютеров (узлов).</span><span class="sxs-lookup"><span data-stu-id="b88c3-117">A [DSC configuration](../configurations/configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (nodes).</span></span>

<span data-ttu-id="b88c3-118">В среде PowerShell ISE введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="b88c3-118">In the PowerShell ISE, type the following:</span></span>

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

<span data-ttu-id="b88c3-119">Сохраните файл как `WebsiteTest.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-119">Save the file as `WebsiteTest.ps1`.</span></span>

<span data-ttu-id="b88c3-120">Как видно, текст выглядит как функция PowerShell, перед именем которой добавлено ключевое слово **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="b88c3-120">You can see that it looks like a PowerShell function, with the addition of the keyword **Configuration** used before the name of the function.</span></span>

<span data-ttu-id="b88c3-121">В блоке **Node** определяется настраиваемый целевой узел.</span><span class="sxs-lookup"><span data-stu-id="b88c3-121">The **Node** block specifies the target node to be configured.</span></span> <span data-ttu-id="b88c3-122">В этом случае — `localhost`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-122">In this case, `localhost`.</span></span>

<span data-ttu-id="b88c3-123">Конфигурация вызывает два [ресурса](../resources/resources.md): **WindowsFeature** и **File**.</span><span class="sxs-lookup"><span data-stu-id="b88c3-123">The configuration calls two [resources](../resources/resources.md), **WindowsFeature** and **File**.</span></span>
<span data-ttu-id="b88c3-124">Ресурсы обеспечивают для целевого узла состояние, определенное в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b88c3-124">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="b88c3-125">Компиляция конфигурации</span><span class="sxs-lookup"><span data-stu-id="b88c3-125">Compile the configuration</span></span>

<span data-ttu-id="b88c3-126">Чтобы применить конфигурацию DSC к узлу, ее сначала нужно скомпилировать в MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="b88c3-126">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="b88c3-127">Для этого запустите конфигурацию как функцию.</span><span class="sxs-lookup"><span data-stu-id="b88c3-127">To do this, you run the configuration like a function.</span></span> <span data-ttu-id="b88c3-128">В консоли PowerShell перейдите к папке с сохраненным файлом конфигурации и выполните следующую команду, чтобы скомпилировать конфигурацию в MOF-файл:</span><span class="sxs-lookup"><span data-stu-id="b88c3-128">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following commands to compile the configuration into a MOF file:</span></span>

```powershell
. .\WebsiteTest.ps1
WebsiteTest
```

<span data-ttu-id="b88c3-129">Будут созданы следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="b88c3-129">This generates the following output:</span></span>

```
Directory: C:\ConfigurationTest\WebsiteTest


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

<span data-ttu-id="b88c3-130">Первая строка делает функцию конфигурации доступной в консоли.</span><span class="sxs-lookup"><span data-stu-id="b88c3-130">The first line makes the configuration function available in the console.</span></span> <span data-ttu-id="b88c3-131">Вторая строка запускает конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b88c3-131">The second line runs the configuration.</span></span> <span data-ttu-id="b88c3-132">Результат — создание папки с именем `WebsiteTest`, которая вложена в текущую папку.</span><span class="sxs-lookup"><span data-stu-id="b88c3-132">The result is that a new folder, named `WebsiteTest` is created as a subfolder of the current folder.</span></span> <span data-ttu-id="b88c3-133">Папка `WebsiteTest` содержит файл с именем `localhost.mof`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-133">The `WebsiteTest` folder contains a file named `localhost.mof`.</span></span> <span data-ttu-id="b88c3-134">Это файл, который затем можно применить к целевому узлу.</span><span class="sxs-lookup"><span data-stu-id="b88c3-134">This is the file that can then be applied to the target node.</span></span>

## <a name="apply-the-configuration"></a><span data-ttu-id="b88c3-135">Применение конфигурации</span><span class="sxs-lookup"><span data-stu-id="b88c3-135">Apply the configuration</span></span>

<span data-ttu-id="b88c3-136">Теперь, когда у вас есть скомпилированный MOF-файл, вы можете применить конфигурацию к целевому узлу (в нашем примере это локальный компьютер), вызвав командлет [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="b88c3-136">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="b88c3-137">Этот командлет `Start-DscConfiguration` сообщает [локальному диспетчеру конфигураций (LCM)](../managing-nodes/metaConfig.md) (ядру DSC) о необходимости применить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b88c3-137">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), which is the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="b88c3-138">LCM вызывает ресурсы DSC для применения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b88c3-138">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="b88c3-139">Чтобы разрешить выполнение DSC, Windows необходимо настроить для получения команд PowerShell из удаленного расположения, даже когда вы запускаете конфигурацию `localhost`.</span><span class="sxs-lookup"><span data-stu-id="b88c3-139">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands, even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="b88c3-140">Чтобы правильно настроить среду, запустите `Set-WsManQuickConfig -Force` в терминале PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="b88c3-140">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="b88c3-141">В консоли PowerShell перейдите к папке с сохраненным файлом конфигурации и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b88c3-141">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following command:</span></span>

```powershell
Start-DscConfiguration .\WebsiteTest
```

## <a name="test-the-configuration"></a><span data-ttu-id="b88c3-142">Тестирование конфигурации</span><span class="sxs-lookup"><span data-stu-id="b88c3-142">Test the configuration</span></span>

<span data-ttu-id="b88c3-143">Чтобы проверить применение конфигурации, можно вызвать командлет [Get DscConfigurationStatus](/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus).</span><span class="sxs-lookup"><span data-stu-id="b88c3-143">You can call the [Get-DscConfigurationStatus](/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus) cmdlet to see whether the configuration succeeded.</span></span>

<span data-ttu-id="b88c3-144">Также можно проверить результаты непосредственным образом. В нашем примере для этого нужно перейти к `http://localhost/` в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="b88c3-144">You can also test the results directly, in this case by browsing to `http://localhost/` in a web browser.</span></span> <span data-ttu-id="b88c3-145">Вы увидите ранее созданную HTML-страницу "Hello World".</span><span class="sxs-lookup"><span data-stu-id="b88c3-145">You should see the "Hello World" HTML page you created as the first step in this example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b88c3-146">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="b88c3-146">Next steps</span></span>

- <span data-ttu-id="b88c3-147">См. дополнительные сведения о [конфигурации DSC](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="b88c3-147">Find out more about DSC configurations at [DSC configurations](../configurations/configurations.md).</span></span>
- <span data-ttu-id="b88c3-148">См. дополнительные сведения о том, как создавать доступные пользовательские [ресурсы DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="b88c3-148">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="b88c3-149">Конфигурации DSC и ресурсы доступны в [коллекции PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="b88c3-149">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
