---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Контрольный список для создания ресурсов
ms.openlocfilehash: 85e0963d46358cd37cb87ea94fe6d1178a4f6a4a
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500610"
---
# <a name="resource-authoring-checklist"></a><span data-ttu-id="e9012-103">Контрольный список для создания ресурсов</span><span class="sxs-lookup"><span data-stu-id="e9012-103">Resource authoring checklist</span></span>

<span data-ttu-id="e9012-104">Это список рекомендаций, которых нужно придерживаться при создании нового ресурса DSC.</span><span class="sxs-lookup"><span data-stu-id="e9012-104">This checklist is a list of best practices when authoring a new DSC Resource.</span></span>

## <a name="resource-module-contains-psd1-file-and-schemamof-for-every-resource"></a><span data-ttu-id="e9012-105">Модуль ресурсов содержит PSD1-файл и SCHEMA.MOF-файл для каждого ресурса</span><span class="sxs-lookup"><span data-stu-id="e9012-105">Resource module contains .psd1 file and schema.mof for every resource</span></span>

<span data-ttu-id="e9012-106">Убедитесь, что ресурс имеет правильную структуру и содержит все необходимые файлы.</span><span class="sxs-lookup"><span data-stu-id="e9012-106">Check that your resource has correct structure and contains all required files.</span></span> <span data-ttu-id="e9012-107">Каждый модуль ресурсов должен содержать PSD1-файл, а каждый несоставной ресурс должен иметь SCHEMA.MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="e9012-107">Every resource module should contain a .psd1 file and every non-composite resource should have schema.mof file.</span></span>
<span data-ttu-id="e9012-108">Ресурсы, которые не содержат схему, не выводятся `Get-DscResource`, и пользователи не смогут использовать IntelliSense при написании кода для этих модулей в интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="e9012-108">Resources that do not contain schema will not be listed by `Get-DscResource` and users will not be able to use the intellisense when writing code against those modules in ISE.</span></span> <span data-ttu-id="e9012-109">Структура каталогов для ресурса xRemoteFile, который является частью [модуля ресурсов xPSDesiredStateConfiguration](https://github.com/PowerShell/xPSDesiredStateConfiguration), выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e9012-109">The directory structure for xRemoteFile resource, which is part of the [xPSDesiredStateConfiguration resource module](https://github.com/PowerShell/xPSDesiredStateConfiguration), looks as follows:</span></span>

```
xPSDesiredStateConfiguration
    DSCResources
        MSFT_xRemoteFile
            MSFT_xRemoteFile.psm1
            MSFT_xRemoteFile.schema.mof
    Examples
        xRemoteFile_DownloadFile.ps1
    ResourceDesignerScripts
        GenerateXRemoteFileSchema.ps1
    Tests
        ResourceDesignerTests.ps1
    xPSDesiredStateConfiguration.psd1
```

## <a name="resource-and-schema-are-correct"></a><span data-ttu-id="e9012-110">Ресурс и схема верны</span><span class="sxs-lookup"><span data-stu-id="e9012-110">Resource and schema are correct</span></span>

<span data-ttu-id="e9012-111">Проверьте файл схемы ресурса (\*.schema.mof).</span><span class="sxs-lookup"><span data-stu-id="e9012-111">Verify the resource schema (\*.schema.mof) file.</span></span> <span data-ttu-id="e9012-112">Для разработки и проверки схемы можно использовать [Конструктор ресурсов DSC](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0).</span><span class="sxs-lookup"><span data-stu-id="e9012-112">You can use the [DSC Resource Designer](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) to help develop and test your schema.</span></span> <span data-ttu-id="e9012-113">Убедитесь, что выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="e9012-113">Make sure that:</span></span>

- <span data-ttu-id="e9012-114">Типы свойств являются правильными (например, не используйте String для свойств, принимающих числовые значения, в таких случаях следует использовать UInt32 или другие числовые типы).</span><span class="sxs-lookup"><span data-stu-id="e9012-114">Property types are correct (e.g. don't use String for properties which accept numeric values, you should use UInt32 or other numeric types instead)</span></span>
- <span data-ttu-id="e9012-115">Атрибуты свойств указаны правильно: ([key], [required], [write], [read]).</span><span class="sxs-lookup"><span data-stu-id="e9012-115">Property attributes are specified correctly as: ([key], [required], [write], [read])</span></span>
- <span data-ttu-id="e9012-116">По меньшей мере один параметр в схеме должен быть помечен как [key].</span><span class="sxs-lookup"><span data-stu-id="e9012-116">At least one parameter in the schema has to be marked as [key]</span></span>
- <span data-ttu-id="e9012-117">Свойство [read] невозможно использовать совместно с любым из следующих свойств: [required], [key], [write].</span><span class="sxs-lookup"><span data-stu-id="e9012-117">[read] property does not coexist together with any of: [required], [key], [write]</span></span>
- <span data-ttu-id="e9012-118">Если указано несколько квалификаторов кроме [read], то [key] имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="e9012-118">If multiple qualifiers are specified except [read], then [key] takes precedence</span></span>
- <span data-ttu-id="e9012-119">Если указаны [write] and [required], то приоритет имеет [required].</span><span class="sxs-lookup"><span data-stu-id="e9012-119">If [write] and [required] are specified, then [required] takes precedence</span></span>
- <span data-ttu-id="e9012-120">Где необходимо, указан ValueMap. Пример:</span><span class="sxs-lookup"><span data-stu-id="e9012-120">ValueMap is specified where appropriate Example:</span></span>

  ```
  [Read, ValueMap{"Present", "Absent"}, Values{"Present", "Absent"}, Description("Says whether DestinationPath exists on the machine")] String Ensure;
  ```

- <span data-ttu-id="e9012-121">Понятное имя указано и соответствует соглашениям об именовании DSC.</span><span class="sxs-lookup"><span data-stu-id="e9012-121">Friendly name is specified and confirms to DSC naming conventions</span></span>

  <span data-ttu-id="e9012-122">Например, `[ClassVersion("1.0.0.0"), FriendlyName("xRemoteFile")]`.</span><span class="sxs-lookup"><span data-stu-id="e9012-122">Example: `[ClassVersion("1.0.0.0"), FriendlyName("xRemoteFile")]`</span></span>

- <span data-ttu-id="e9012-123">Каждое поле имеет осмысленное описание.</span><span class="sxs-lookup"><span data-stu-id="e9012-123">Every field has meaningful description.</span></span> <span data-ttu-id="e9012-124">В репозитории GitHub PowerShell есть хорошие примеры, такие как [схема .schema.mof для xRemoteFile](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/DSCResources/DSC_xRemoteFile/DSC_xRemoteFile.schema.mof).</span><span class="sxs-lookup"><span data-stu-id="e9012-124">The PowerShell GitHub repository has good examples, such as the [.schema.mof for xRemoteFile](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/DSCResources/DSC_xRemoteFile/DSC_xRemoteFile.schema.mof)</span></span>

<span data-ttu-id="e9012-125">Кроме того, следует использовать командлеты **Test-xDscResource** и **Test-xDscSchema** из [Конструктора ресурсов DSC](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) для автоматической проверки ресурса и схемы.</span><span class="sxs-lookup"><span data-stu-id="e9012-125">Additionally, you should use **Test-xDscResource** and **Test-xDscSchema** cmdlets from [DSC Resource Designer](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) to automatically verify the resource and schema:</span></span>

```
Test-xDscResource <Resource_folder>
Test-xDscSchema <Path_to_resource_schema_file>
```

<span data-ttu-id="e9012-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9012-126">For example:</span></span>

```powershell
Test-xDscResource ..\DSCResources\MSFT_xRemoteFile
Test-xDscSchema ..\DSCResources\MSFT_xRemoteFile\MSFT_xRemoteFile.schema.mof
```

## <a name="resource-loads-without-errors"></a><span data-ttu-id="e9012-127">Ресурс загружается без ошибок</span><span class="sxs-lookup"><span data-stu-id="e9012-127">Resource loads without errors</span></span>

<span data-ttu-id="e9012-128">Проверьте, загружен ли модуль ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e9012-128">Check whether the resource module can be successfully loaded.</span></span> <span data-ttu-id="e9012-129">Это можно сделать вручную, выполнив команду `Import-Module <resource_module> -force` и убедившись в отсутствии ошибок, или создав средства автоматизированного тестирования.</span><span class="sxs-lookup"><span data-stu-id="e9012-129">This can be achieved manually, by running `Import-Module <resource_module> -force` and confirming that no errors occurred, or by writing test automation.</span></span> <span data-ttu-id="e9012-130">В последнем случае вы можете применить для тестового случая приведенную ниже структуру:</span><span class="sxs-lookup"><span data-stu-id="e9012-130">In case of the latter, you can follow this structure in your test case:</span></span>

```powershell
$error = $null
Import-Module <resource_module> –force
If ($error.count –ne 0) {
    Throw "Module was not imported correctly. Errors returned: $error"
}
```

## <a name="resource-is-idempotent-in-the-positive-case"></a><span data-ttu-id="e9012-131">В положительном случае ресурс является идемпотентным.</span><span class="sxs-lookup"><span data-stu-id="e9012-131">Resource is idempotent in the positive case</span></span>

<span data-ttu-id="e9012-132">Одной из фундаментальных характеристик ресурсов DSC является идемпотентность.</span><span class="sxs-lookup"><span data-stu-id="e9012-132">One of the fundamental characteristics of DSC resources is idempotence.</span></span> <span data-ttu-id="e9012-133">Это означает, что при каждом применении конфигурации DSC, содержащей этот ресурс, результаты будут одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="e9012-133">It means that applying a DSC configuration containing that resource multiple times will always achieve the same result.</span></span> <span data-ttu-id="e9012-134">Например, если мы создадим конфигурацию со следующим файлом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e9012-134">For example, if we create a configuration which contains the following File resource:</span></span>

```powershell
File file {
    DestinationPath = "C:\test\test.txt"
    Contents = "Sample text"
}
```

<span data-ttu-id="e9012-135">После первого ее применения файл test.txt должен появиться в папке `C:\test`.</span><span class="sxs-lookup"><span data-stu-id="e9012-135">After applying it for the first time, file test.txt should appear in `C:\test` folder.</span></span> <span data-ttu-id="e9012-136">Однако последующие запуски с такой же конфигурацией не должны изменять состояние компьютера (например, не должны создаваться копии файла `test.txt`).</span><span class="sxs-lookup"><span data-stu-id="e9012-136">However, subsequent runs of the same configuration should not change the state of the machine (e.g. no copies of the `test.txt` file should be created).</span></span> <span data-ttu-id="e9012-137">Для подтверждения идемпотентности ресурса можно несколько раз вызвать командлет `Set-TargetResource` при тестировании ресурса напрямую или командлет `Start-DscConfiguration` при комплексном тестировании.</span><span class="sxs-lookup"><span data-stu-id="e9012-137">To ensure a resource is idempotent you can repeatedly call `Set-TargetResource` when testing the resource directly, or call `Start-DscConfiguration` multiple times when doing end to end testing.</span></span> <span data-ttu-id="e9012-138">Результат должен быть идентичным после каждого запуска.</span><span class="sxs-lookup"><span data-stu-id="e9012-138">The result should be the same after every run.</span></span>

## <a name="test-user-modification-scenario"></a><span data-ttu-id="e9012-139">Проверка сценария с изменением пользователя</span><span class="sxs-lookup"><span data-stu-id="e9012-139">Test user modification scenario</span></span>

<span data-ttu-id="e9012-140">Изменив состояние компьютера и повторно запустив DSC, можно убедиться, что командлеты `Set-TargetResource` и `Test-TargetResource` работают правильно.</span><span class="sxs-lookup"><span data-stu-id="e9012-140">By changing the state of the machine and then rerunning DSC, you can verify that `Set-TargetResource` and `Test-TargetResource` function properly.</span></span> <span data-ttu-id="e9012-141">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9012-141">Here are steps you should take:</span></span>

1. <span data-ttu-id="e9012-142">Используйте ресурс, состояние которого отличается от нужного.</span><span class="sxs-lookup"><span data-stu-id="e9012-142">Start with the resource not in the desired state.</span></span>
2. <span data-ttu-id="e9012-143">Запустите конфигурацию с этим ресурсом.</span><span class="sxs-lookup"><span data-stu-id="e9012-143">Run configuration with your resource</span></span>
3. <span data-ttu-id="e9012-144">Проверьте, что `Test-DscConfiguration` возвращает значение True.</span><span class="sxs-lookup"><span data-stu-id="e9012-144">Verify `Test-DscConfiguration` returns True</span></span>
4. <span data-ttu-id="e9012-145">Измените настроенный элемент так, чтобы он находился не в требуемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="e9012-145">Modify the configured item to be out of the desired state</span></span>
5. <span data-ttu-id="e9012-146">Проверьте, что `Test-DscConfiguration` возвращает значение False.</span><span class="sxs-lookup"><span data-stu-id="e9012-146">Verify `Test-DscConfiguration` returns false</span></span>

<span data-ttu-id="e9012-147">Вот более конкретный пример для ресурса реестра:</span><span class="sxs-lookup"><span data-stu-id="e9012-147">Here's a more concrete example using Registry resource:</span></span>

1. <span data-ttu-id="e9012-148">Используйте раздел реестра, состояние которого отличается от нужного.</span><span class="sxs-lookup"><span data-stu-id="e9012-148">Start with registry key not in the desired state</span></span>
2. <span data-ttu-id="e9012-149">Запустите `Start-DscConfiguration` с конфигурацией, чтобы переключить его в нужное состояние, и убедитесь в прохождении проверки.</span><span class="sxs-lookup"><span data-stu-id="e9012-149">Run `Start-DscConfiguration` with a configuration to put it in the desired state and verify it passes.</span></span>
3. <span data-ttu-id="e9012-150">Запустите `Test-DscConfiguration` и убедитесь, что возвращается значение true.</span><span class="sxs-lookup"><span data-stu-id="e9012-150">Run `Test-DscConfiguration` and verify it returns true</span></span>
4. <span data-ttu-id="e9012-151">Измените значение раздела, чтобы он находился не в требуемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="e9012-151">Modify the value of the key so that it is not in the desired state</span></span>
5. <span data-ttu-id="e9012-152">Запустите `Test-DscConfiguration` и убедитесь, что возвращается значение false.</span><span class="sxs-lookup"><span data-stu-id="e9012-152">Run `Test-DscConfiguration` and verify it returns false</span></span>
6. <span data-ttu-id="e9012-153">Функциональность `Get-TargetResource` была проверена с помощью командлета `Get-DscConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="e9012-153">`Get-TargetResource` functionality was verified using `Get-DscConfiguration`</span></span>

<span data-ttu-id="e9012-154">`Get-TargetResource` должен возвращать сведения о текущем состоянии ресурса.</span><span class="sxs-lookup"><span data-stu-id="e9012-154">`Get-TargetResource` should return details of the current state of the resource.</span></span> <span data-ttu-id="e9012-155">Обязательно проверьте результат, вызвав командлет `Get-DscConfiguration` после применения конфигурации и убедившись, что выходные данные правильно отражают текущее состояние компьютера.</span><span class="sxs-lookup"><span data-stu-id="e9012-155">Make sure to test it by calling `Get-DscConfiguration` after you apply the configuration and verifying that output correctly reflects the current state of the machine.</span></span> <span data-ttu-id="e9012-156">Очень важно тестировать его отдельно, поскольку все проблемы в этой области не проявляются при вызове `Start-DscConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="e9012-156">It's important to test it separately, since any issues in this area won't appear when calling `Start-DscConfiguration`.</span></span>

## <a name="call-getsettest-targetresource-functions-directly"></a><span data-ttu-id="e9012-157">Вызов функций **Get/Set/Test-TargetResource** напрямую</span><span class="sxs-lookup"><span data-stu-id="e9012-157">Call **Get/Set/Test-TargetResource** functions directly</span></span>

<span data-ttu-id="e9012-158">Убедитесь, что функции **Get/Set/Test-TargetResource**, реализованные в ресурсе, протестированы (вызваны напрямую и проверены на предмет правильной работы).</span><span class="sxs-lookup"><span data-stu-id="e9012-158">Make sure you test the **Get/Set/Test-TargetResource** functions implemented in your resource by calling them directly and verifying that they work as expected.</span></span>

## <a name="verify-end-to-end-using-start-dscconfiguration"></a><span data-ttu-id="e9012-159">Комплексная проверка с помощью командлета **Start-DscConfiguration**</span><span class="sxs-lookup"><span data-stu-id="e9012-159">Verify End to End using **Start-DscConfiguration**</span></span>

<span data-ttu-id="e9012-160">Тестирование функций **Get/Set и тест-TargetResource** посредством вызова их напрямую имеет важное значение, однако не позволяет выявить все проблемы.</span><span class="sxs-lookup"><span data-stu-id="e9012-160">Testing **Get/Set/Test-TargetResource** functions by calling them directly is important, but not all issues will be discovered this way.</span></span> <span data-ttu-id="e9012-161">Значительная часть тестирования должна быть направлена на использование `Start-DscConfiguration` или опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="e9012-161">You should focus significant part of your testing on using `Start-DscConfiguration` or the pull server.</span></span> <span data-ttu-id="e9012-162">На самом деле именно так пользователи и будут использовать ресурс, поэтому не стоит недооценивать важность таких тестов.</span><span class="sxs-lookup"><span data-stu-id="e9012-162">In fact, this is how users will use the resource, so don't underestimate the significance of this type of tests.</span></span> <span data-ttu-id="e9012-163">Возможные типы проблем.</span><span class="sxs-lookup"><span data-stu-id="e9012-163">Possible types of issues:</span></span>

- <span data-ttu-id="e9012-164">Учетные данные или сеанса могут работать по-разному, так как агент DSC выполняется как служба.</span><span class="sxs-lookup"><span data-stu-id="e9012-164">Credential/Session may behave differently because the DSC agent runs as a service.</span></span> <span data-ttu-id="e9012-165">Обязательно выполните комплексное тестирование всех этих функций.</span><span class="sxs-lookup"><span data-stu-id="e9012-165">Be sure to test any features here end to end.</span></span>
- <span data-ttu-id="e9012-166">Ошибки, выдаваемые командлетом `Start-DscConfiguration`, могут отличаться от ошибок, отображаемых при вызове функции `Set-TargetResource` напрямую.</span><span class="sxs-lookup"><span data-stu-id="e9012-166">Errors output by `Start-DscConfiguration` may be different than those displayed when calling the `Set-TargetResource` function directly.</span></span>

## <a name="test-compatibility-on-all-dsc-supported-platforms"></a><span data-ttu-id="e9012-167">Проверка совместимости на всех платформах, поддерживаемых DSC</span><span class="sxs-lookup"><span data-stu-id="e9012-167">Test compatibility on all DSC supported platforms</span></span>

<span data-ttu-id="e9012-168">Ресурс должен работать на всех платформах, поддерживаемых DSC (Windows Server 2008 R2 и более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="e9012-168">Resource should work on all DSC supported platforms (Windows Server 2008 R2 and newer).</span></span> <span data-ttu-id="e9012-169">Для получения последней версии DSC установите последнюю версию WMF (Windows Management Framework) в своей операционной системе.</span><span class="sxs-lookup"><span data-stu-id="e9012-169">Install the latest WMF (Windows Management Framework) on your OS to get the latest version of DSC.</span></span> <span data-ttu-id="e9012-170">Если ресурс по своей природе не поддерживает некоторые из этих платформ, должно быть возвращено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e9012-170">If your resource does not work on some of these platforms by design, a specific error message should be returned.</span></span> <span data-ttu-id="e9012-171">Кроме того, убедитесь, что ресурс проверяет, присутствуют ли вызываемые командлеты на конкретном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e9012-171">Also, make sure your resource checks whether cmdlets you are calling are present on particular machine.</span></span> <span data-ttu-id="e9012-172">В Windows Server 2012 было добавлено большое количество новых командлетов, которые недоступны в Windows Server 2008 R2 даже при установленном WMF.</span><span class="sxs-lookup"><span data-stu-id="e9012-172">Windows Server 2012 added a large number of new cmdlets that are not available on Windows Server 2008R2, even with WMF installed.</span></span>

## <a name="verify-on-windows-client-if-applicable"></a><span data-ttu-id="e9012-173">Проверка на клиенте Windows (если применимо)</span><span class="sxs-lookup"><span data-stu-id="e9012-173">Verify on Windows Client (if applicable)</span></span>

<span data-ttu-id="e9012-174">При тестировании довольно часто допускается упущение, заключающееся в проверке ресурса только в серверных версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="e9012-174">One very common test gap is verifying the resource only on server versions of Windows.</span></span> <span data-ttu-id="e9012-175">Многие ресурсы также предназначены для работы в клиентских SKU. Если это характерно для вашего случая, не забудьте проверить ресурс и на этих платформах также.</span><span class="sxs-lookup"><span data-stu-id="e9012-175">Many resources are also designed to work on Client SKUs, so if that's true in your case, don't forget to test it on those platforms as well.</span></span>

## <a name="get-dscresource-lists-the-resource"></a><span data-ttu-id="e9012-176">Get-DSCResource указывает ресурс</span><span class="sxs-lookup"><span data-stu-id="e9012-176">Get-DSCResource lists the resource</span></span>

<span data-ttu-id="e9012-177">При вызове командлета `Get-DscResource` после развертывания модуля ваш ресурс должен отображаться вместе с другими в списке результатов.</span><span class="sxs-lookup"><span data-stu-id="e9012-177">After deploying the module, calling `Get-DscResource` should list your resource among others as a result.</span></span> <span data-ttu-id="e9012-178">Если ресурс отсутствует в списке, убедитесь, что для этого ресурса существует SCHEMA.MOF-файл.</span><span class="sxs-lookup"><span data-stu-id="e9012-178">If you can't find your resource in the list, make sure that schema.mof file for that resource exists.</span></span>

## <a name="resource-module-contains-examples"></a><span data-ttu-id="e9012-179">Модуль ресурсов содержит примеры</span><span class="sxs-lookup"><span data-stu-id="e9012-179">Resource module contains examples</span></span>

<span data-ttu-id="e9012-180">Создавайте качественные примеры, которые помогут другим пользователям понять, как работать с модулем ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e9012-180">Creating quality examples which will help others understand how to use it.</span></span> <span data-ttu-id="e9012-181">Это особенно важно, потому что многие пользователи рассматривают пример кода в качестве документации.</span><span class="sxs-lookup"><span data-stu-id="e9012-181">This is crucial, especially since many users treat sample code as documentation.</span></span>

- <span data-ttu-id="e9012-182">Во-первых, необходимо определить примеры, которые будут включены в модуль; они по меньшей мере должны охватывать наиболее важные варианты использования ресурса:</span><span class="sxs-lookup"><span data-stu-id="e9012-182">First, you should determine the examples that will be included with the module – at minimum, you should cover most important use cases for your resource:</span></span>
- <span data-ttu-id="e9012-183">Если модуль содержит несколько ресурсов, которые должны работать вместе в рамках комплексного сценария, в качестве первого оптимально подойдет простой комплексный пример.</span><span class="sxs-lookup"><span data-stu-id="e9012-183">If your module contains several resources that need to work together for an end-to-end scenario, the basic end-to-end example would ideally be first.</span></span>
- <span data-ttu-id="e9012-184">Начальные примеры должны быть очень простыми — начало работы с ресурсами в небольших управляемых фрагментах (например, создание нового виртуального жесткого диска).</span><span class="sxs-lookup"><span data-stu-id="e9012-184">The initial examples should be very simple -- how to get started with your resources in small manageable chunks (e.g. creating a new VHD)</span></span>
- <span data-ttu-id="e9012-185">Последующие примеры должны основываться на начальных (например, создание виртуальной машины из виртуального жесткого диска, ее удаление и изменение) и демонстрировать расширенные функциональные возможности (например, создание виртуальной машины с динамической памятью).</span><span class="sxs-lookup"><span data-stu-id="e9012-185">Subsequent examples should build on those examples (e.g. creating a VM from a VHD, removing VM, modifying VM), and show advanced functionality (e.g. creating a VM with dynamic memory)</span></span>
- <span data-ttu-id="e9012-186">Примеры конфигурации должны быть параметризованными (все значения должны передаваться конфигурации в качестве параметров, а жестко закодированные значения должны отсутствовать):</span><span class="sxs-lookup"><span data-stu-id="e9012-186">Example configurations should be parameterized (all values should be passed to the configuration as parameters and there should be no hardcoded values):</span></span>

  ```powershell
  configuration Sample_xRemoteFile_DownloadFile
  {
    param
    (
        [string[]] $nodeName = 'localhost',

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $destinationPath,

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $uri,

        [String] $userAgent,

        [Hashtable] $headers
    )

    Import-DscResource -Name MSFT_xRemoteFile -ModuleName xPSDesiredStateConfiguration

    Node $nodeName
    {
        xRemoteFile DownloadFile
        {
            DestinationPath = $destinationPath
            Uri = $uri
            UserAgent = $userAgent
            Headers = $headers
        }
    }
  }
  ```

- <span data-ttu-id="e9012-187">Рекомендуется включить (закомментировать) в конце примера сценария образец вызова конфигурации с фактическими значениями.</span><span class="sxs-lookup"><span data-stu-id="e9012-187">It's a good practice to include (commented out) example of how to call the configuration with the actual values at the end of the example script.</span></span> <span data-ttu-id="e9012-188">Например, в приведенной выше конфигурации не совсем очевидно, что лучше всего указать UserAgent следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e9012-188">For example, in the configuration above it isn't necessarily obvious that the best way to specify UserAgent is:</span></span>

  <span data-ttu-id="e9012-189">`UserAgent = [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer` В этом случае можно пояснить, как будет выполнена конфигурация, с помощью следующего комментария.</span><span class="sxs-lookup"><span data-stu-id="e9012-189">`UserAgent = [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer` In which case a comment can clarify the intended execution of the configuration:</span></span>

  ```powershell
  <#
  Sample use (parameter values need to be changed according to your scenario):

  Sample_xRemoteFile_DownloadFile -destinationPath "$env:SystemDrive\fileName.jpg" -uri "http://www.contoso.com/image.jpg"

  Sample_xRemoteFile_DownloadFile -destinationPath "$env:SystemDrive\fileName.jpg" -uri "http://www.contoso.com/image.jpg" `
  -userAgent [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer -headers @{"Accept-Language" = "en-US"}
  #>
  ```

- <span data-ttu-id="e9012-190">Для каждого примера укажите краткое описание его назначение и параметров.</span><span class="sxs-lookup"><span data-stu-id="e9012-190">For each example, write a short description which explains what it does, and the meaning of the parameters.</span></span>
- <span data-ttu-id="e9012-191">Убедитесь, что примеры охватывают большинство важных сценариев для ресурса, а если все нужное присутствует, убедитесь, что они выполняют и переводят компьютер в нужное состояние.</span><span class="sxs-lookup"><span data-stu-id="e9012-191">Make sure examples cover most the important scenarios for your resource and if there's nothing missing, verify that they all execute and put machine in the desired state.</span></span>

## <a name="error-messages-are-easy-to-understand-and-help-users-solve-problems"></a><span data-ttu-id="e9012-192">Сообщения об ошибках просты для понимания и помогают пользователям устранять проблемы</span><span class="sxs-lookup"><span data-stu-id="e9012-192">Error messages are easy to understand and help users solve problems</span></span>

<span data-ttu-id="e9012-193">Грамотный подход к сообщениям об ошибках должен отвечать следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="e9012-193">Good error messages should be:</span></span>

- <span data-ttu-id="e9012-194">Наличие: самым большим недостатком сообщений об ошибках является их частое отсутствие, поэтому убедитесь, что они существуют.</span><span class="sxs-lookup"><span data-stu-id="e9012-194">There: The biggest problem with error messages is that they often don't exist, so make sure they are there.</span></span>
- <span data-ttu-id="e9012-195">Простота восприятия: естественный язык без малопонятных кодов.</span><span class="sxs-lookup"><span data-stu-id="e9012-195">Easy to understand: Human readable, no obscure error codes</span></span>
- <span data-ttu-id="e9012-196">Точность: объясните, в чем именно заключается проблема.</span><span class="sxs-lookup"><span data-stu-id="e9012-196">Precise: Describe what's exactly the problem</span></span>
- <span data-ttu-id="e9012-197">Конструктивность: приведите советы по устранению.</span><span class="sxs-lookup"><span data-stu-id="e9012-197">Constructive: Advice how to fix the issue</span></span>
- <span data-ttu-id="e9012-198">Вежливость: не обвиняйте пользователя и не заставляйте его чувствовать себя некомфортно.</span><span class="sxs-lookup"><span data-stu-id="e9012-198">Polite: Don't blame user or make them feel bad</span></span>

<span data-ttu-id="e9012-199">Обязательно проверяйте ошибки в комплексных сценариях (с помощью `Start-DscConfiguration`), так как они могут отличаться от тех, которые возвращаются при выполнении функций ресурсов напрямую.</span><span class="sxs-lookup"><span data-stu-id="e9012-199">Make sure you verify errors in End to End scenarios (using `Start-DscConfiguration`), because they may differ from those returned when running resource functions directly.</span></span>

## <a name="log-messages-are-easy-to-understand-and-informative-including-verbose-debug-and-etw-logs"></a><span data-ttu-id="e9012-200">Сообщения журнала просты для понимания и информативны (включая журналы –verbose, –debug и трассировки событий Windows)</span><span class="sxs-lookup"><span data-stu-id="e9012-200">Log messages are easy to understand and informative (including –verbose, –debug and ETW logs)</span></span>

<span data-ttu-id="e9012-201">Убедитесь, что выводимые ресурсом журналы просты для понимания и представляют ценность для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9012-201">Ensure that logs outputted by the resource are easy to understand and provide value to the user.</span></span>
<span data-ttu-id="e9012-202">Ресурсы должны выводить все сведения, которые могут оказаться полезными для пользователя, однако ведение максимального числа всевозможных журналов не всегда является лучшим решением.</span><span class="sxs-lookup"><span data-stu-id="e9012-202">Resources should output all information which might be helpful to the user, but more logs is not always better.</span></span> <span data-ttu-id="e9012-203">Следует избегать избыточности и вывода данных, которые не представляют никакой ценности. Не заставляйте людей просматривать сотни записей в журналах для поиска необходимых сведений.</span><span class="sxs-lookup"><span data-stu-id="e9012-203">You should avoid redundancy and outputting data which does not provide additional value – don't make someone go through hundreds of log entries in order to find what they're looking for.</span></span> <span data-ttu-id="e9012-204">Конечно же, полное отсутствие журналов также не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="e9012-204">Of course, no logs is not an acceptable solution for this problem either.</span></span>

<span data-ttu-id="e9012-205">При тестировании следует проанализировать журналы подробных сведений и отладки (запустив `Start-DscConfiguration` с параметрами `–Verbose` и `–Debug`), а также журналы трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="e9012-205">When testing, you should also analyze verbose and debug logs (by running `Start-DscConfiguration` with `–Verbose` and `–Debug` switches appropriately), as well as ETW logs.</span></span> <span data-ttu-id="e9012-206">Чтобы просмотреть DSC-журналы трассировки событий Windows, перейдите в средство просмотра событий и откройте следующую папку: Приложения и службы, Microsoft, Windows, Настройка требуемого состояния.</span><span class="sxs-lookup"><span data-stu-id="e9012-206">To see DSC ETW logs, go to Event Viewer and open the following folder: Applications and Services- Microsoft - Windows - Desired State Configuration.</span></span> <span data-ttu-id="e9012-207">По умолчанию будет доступен операционный канал; также включите каналы аналитики и отладки (это необходимо сделать перед запуском конфигурации).</span><span class="sxs-lookup"><span data-stu-id="e9012-207">By default there will be Operational channel, but make sure you enable Analytic and Debug channels before running the configuration.</span></span> <span data-ttu-id="e9012-208">Чтобы включить каналы аналитики и отладки, можно выполнить следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="e9012-208">To enable Analytic/Debug channels, you can execute script below:</span></span>

```powershell
$statusEnabled = $true
# Use "Analytic" to enable Analytic channel
$eventLogFullName = "Microsoft-Windows-Dsc/Debug"
$commandToExecute = "wevtutil set-log $eventLogFullName /e:$statusEnabled /q:$statusEnabled   "
$log = New-Object System.Diagnostics.Eventing.Reader.EventLogConfiguration $eventLogFullName
if($statusEnabled -eq $log.IsEnabled)
{
    Write-Host -Verbose "The channel event log is already enabled"
    return
}
Invoke-Expression $commandToExecute
```

## <a name="resource-implementation-does-not-contain-hardcoded-paths"></a><span data-ttu-id="e9012-209">Реализация ресурса не содержит жестко заданные пути</span><span class="sxs-lookup"><span data-stu-id="e9012-209">Resource implementation does not contain hardcoded paths</span></span>

<span data-ttu-id="e9012-210">Убедитесь, в реализации ресурса нет ни одного жестко заданного пути, особенно в том случае, если они предполагают язык (en-us) или имеются системные переменные, которые могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="e9012-210">Ensure there are no hardcoded paths in the resource implementation, particularly if they assume language (en-us), or when there are system variables that can be used.</span></span> <span data-ttu-id="e9012-211">Если ресурсу требуется доступ к определенным путям, используйте переменные среды вместо жесткого задания пути, так как на других компьютерах он может отличаться.</span><span class="sxs-lookup"><span data-stu-id="e9012-211">If your resource need to access specific paths, use environment variables instead of hardcoding the path, as it may differ on other machines.</span></span>

<span data-ttu-id="e9012-212">Пример</span><span class="sxs-lookup"><span data-stu-id="e9012-212">Example:</span></span>

<span data-ttu-id="e9012-213">Вместо:</span><span class="sxs-lookup"><span data-stu-id="e9012-213">Instead of:</span></span>

```powershell
$tempPath = "C:\Users\kkaczma\AppData\Local\Temp\MyResource"
$programFilesPath = "C:\Program Files (x86)"
```

<span data-ttu-id="e9012-214">Можно написать:</span><span class="sxs-lookup"><span data-stu-id="e9012-214">You can write:</span></span>

```powershell
$tempPath = Join-Path $env:temp "MyResource"
$programFilesPath = ${env:ProgramFiles(x86)}
```

## <a name="resource-implementation-does-not-contain-user-information"></a><span data-ttu-id="e9012-215">Реализация ресурса не содержит сведения о пользователе</span><span class="sxs-lookup"><span data-stu-id="e9012-215">Resource implementation does not contain user information</span></span>

<span data-ttu-id="e9012-216">Убедитесь, что в коде отсутствуют адреса электронной почты, сведения об учетной записи или имена людей.</span><span class="sxs-lookup"><span data-stu-id="e9012-216">Make sure there are no email names, account information, or names of people in the code.</span></span>

## <a name="resource-was-tested-with-validinvalid-credentials"></a><span data-ttu-id="e9012-217">Ресурс был протестирован с допустимыми и недопустимыми учетными данными</span><span class="sxs-lookup"><span data-stu-id="e9012-217">Resource was tested with valid/invalid credentials</span></span>

<span data-ttu-id="e9012-218">Если ресурс принимает учетные данные в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="e9012-218">If your resource takes a credential as parameter:</span></span>

- <span data-ttu-id="e9012-219">Проверьте работу ресурса при отсутствии доступа у учетной записи Local System (или учетной записи компьютера для удаленных ресурсов).</span><span class="sxs-lookup"><span data-stu-id="e9012-219">Verify the resource works when Local System (or the computer account for remote resources) does not have access.</span></span>
- <span data-ttu-id="e9012-220">Убедитесь, что ресурс работает с учетными данными, указанными для Get, Set и Test</span><span class="sxs-lookup"><span data-stu-id="e9012-220">Verify the resource works with a credential specified for Get, Set and Test</span></span>
- <span data-ttu-id="e9012-221">Если ресурс обращается к общим ресурсам, протестируйте все варианты, которые должны поддерживаться, например следующие.</span><span class="sxs-lookup"><span data-stu-id="e9012-221">If your resource accesses shares, test all the variants you need to support, such as:</span></span>
  - <span data-ttu-id="e9012-222">Стандартные общие ресурсы Windows.</span><span class="sxs-lookup"><span data-stu-id="e9012-222">Standard windows shares.</span></span>
  - <span data-ttu-id="e9012-223">Общие ресурсы DFS.</span><span class="sxs-lookup"><span data-stu-id="e9012-223">DFS shares.</span></span>
  - <span data-ttu-id="e9012-224">Общие ресурсы SAMBA (если требуется поддержка Linux).</span><span class="sxs-lookup"><span data-stu-id="e9012-224">SAMBA shares (if you want to support Linux.)</span></span>

## <a name="resource-does-not-require-interactive-input"></a><span data-ttu-id="e9012-225">Ресурс не требует интерактивного ввода</span><span class="sxs-lookup"><span data-stu-id="e9012-225">Resource does not require interactive input</span></span>

<span data-ttu-id="e9012-226">Функции **Get/Set/Test-TargetResource** должны выполняться автоматически и не ожидать ввода данных пользователем на любом этапе выполнения (например, не следует использовать `Get-Credential` внутри этих функций).</span><span class="sxs-lookup"><span data-stu-id="e9012-226">**Get/Set/Test-TargetResource** functions should be executed automatically and must not wait for user's input at any stage of execution (e.g. you should not use `Get-Credential` inside these functions).</span></span> <span data-ttu-id="e9012-227">Если необходимо предоставить вводимые пользователем данные, их следует передать в конфигурацию в качестве параметра на этапе компиляции.</span><span class="sxs-lookup"><span data-stu-id="e9012-227">If you need to provide user's input, you should pass it to the configuration as parameter during the compilation phase.</span></span>

## <a name="resource-functionality-was-thoroughly-tested"></a><span data-ttu-id="e9012-228">Функциональность ресурса была тщательно протестирована</span><span class="sxs-lookup"><span data-stu-id="e9012-228">Resource functionality was thoroughly tested</span></span>

<span data-ttu-id="e9012-229">Этот контрольный список содержит элементы, которые важны для тестирования и/или часто пропускаются.</span><span class="sxs-lookup"><span data-stu-id="e9012-229">This checklist contains items which are important to be tested and/or are often missed.</span></span> <span data-ttu-id="e9012-230">Будет проведено несколько тестов, главным образом функциональных, которые предназначены для тестируемого вами ресурса и здесь не упомянуты.</span><span class="sxs-lookup"><span data-stu-id="e9012-230">There will be bunch of tests, mainly functional ones which will be specific to the resource you are testing and are not mentioned here.</span></span> <span data-ttu-id="e9012-231">Не забывайте об отрицательных тестовых случаях.</span><span class="sxs-lookup"><span data-stu-id="e9012-231">Don't forget about negative test cases.</span></span>

## <a name="best-practice-resource-module-contains-tests-folder-with-resourcedesignertestsps1-script"></a><span data-ttu-id="e9012-232">Рекомендация: модуль ресурсов содержит папку Tests со скриптом ResourceDesignerTests.ps1.</span><span class="sxs-lookup"><span data-stu-id="e9012-232">Best practice: Resource module contains Tests folder with ResourceDesignerTests.ps1 script</span></span>

<span data-ttu-id="e9012-233">Рекомендуется создать папку Tests внутри модуля ресурсов, создать файл `ResourceDesignerTests.ps1` и с помощью **Test-xDscResource** и **Test-xDscSchema** добавить тесты для всех ресурсов в заданном модуле.</span><span class="sxs-lookup"><span data-stu-id="e9012-233">It's a good practice to create folder "Tests" inside resource module, create `ResourceDesignerTests.ps1` file and add tests using **Test-xDscResource** and **Test-xDscSchema** for all resources in given module.</span></span> <span data-ttu-id="e9012-234">Так можно быстро проверить все ресурсы из заданных модулей, а также проверить их работоспособность перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="e9012-234">This way you can quickly validate schemas of all resources from the given modules and do a sanity check before publishing.</span></span> <span data-ttu-id="e9012-235">Для xRemoteFile файл `ResourceTests.ps1` может иметь просто вид:</span><span class="sxs-lookup"><span data-stu-id="e9012-235">For xRemoteFile, `ResourceTests.ps1` could look as simple as:</span></span>

```powershell
Test-xDscResource ..\DSCResources\MSFT_xRemoteFile
Test-xDscSchema ..\DSCResources\MSFT_xRemoteFile\MSFT_xRemoteFile.schema.mof
```

## <a name="best-practice-resource-folder-contains-resource-designer-script-for-generating-schema"></a><span data-ttu-id="e9012-236">Рекомендация: папка Resource содержит сценарий конструктора ресурсов для создания схемы.</span><span class="sxs-lookup"><span data-stu-id="e9012-236">Best practice: Resource folder contains resource designer script for generating schema</span></span>

<span data-ttu-id="e9012-237">Каждый ресурс должен содержать сценарий конструктора ресурсов, создающий MOF-схему для данного ресурса.</span><span class="sxs-lookup"><span data-stu-id="e9012-237">Each resource should contain a resource designer script which generates a mof schema of the resource.</span></span> <span data-ttu-id="e9012-238">Этот файл следует поместить в каталог `<ResourceName>\ResourceDesignerScripts` и назвать Generate`<ResourceName>Schema.ps1`. Для ресурса xRemoteFile этот файл будет называться `GenerateXRemoteFileSchema.ps1` и содержать следующее.</span><span class="sxs-lookup"><span data-stu-id="e9012-238">This file should be placed in `<ResourceName>\ResourceDesignerScripts` and be named Generate `<ResourceName>Schema.ps1` For xRemoteFile resource this file would be called `GenerateXRemoteFileSchema.ps1` and contain:</span></span>

```powershell
$DestinationPath = New-xDscResourceProperty -Name DestinationPath -Type String -Attribute Key -Description 'Path under which downloaded or copied file should be accessible after operation.'
$Uri = New-xDscResourceProperty -Name Uri -Type String -Attribute Required -Description 'Uri of a file which should be copied or downloaded. This parameter supports HTTP and HTTPS values.'
$Headers = New-xDscResourceProperty -Name Headers -Type Hashtable[] -Attribute Write -Description 'Headers of the web request.'
$UserAgent = New-xDscResourceProperty -Name UserAgent -Type String -Attribute Write -Description 'User agent for the web request.'
$Ensure = New-xDscResourceProperty -Name Ensure -Type String -Attribute Read -ValidateSet "Present", "Absent" -Description 'Says whether DestinationPath exists on the machine'
$Credential = New-xDscResourceProperty -Name Credential -Type PSCredential -Attribute Write -Description 'Specifies a user account that has permission to send the request.'
$CertificateThumbprint = New-xDscResourceProperty -Name CertificateThumbprint -Type String -Attribute Write -Description 'Digital public key certificate that is used to send the request.'

New-xDscResource -Name MSFT_xRemoteFile -Property @($DestinationPath, $Uri, $Headers, $UserAgent, $Ensure, $Credential, $CertificateThumbprint) -ModuleName xPSDesiredStateConfiguration2 -FriendlyName xRemoteFile
```

## <a name="best-practice-resource-supports--whatif"></a><span data-ttu-id="e9012-239">Рекомендация: ресурс поддерживает -WhatIf.</span><span class="sxs-lookup"><span data-stu-id="e9012-239">Best practice: Resource supports -WhatIf</span></span>

<span data-ttu-id="e9012-240">Если ресурс выполняет "небезопасные" операции, рекомендуется реализовать функциональность `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="e9012-240">If your resource is performing "dangerous" operations, it's a good practice to implement `-WhatIf` functionality.</span></span> <span data-ttu-id="e9012-241">После этого убедитесь в том, что выходные данные `-WhatIf` правильно описывают операции, которые могут быть выполнены при запуске команды без параметра `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="e9012-241">After it's done, make sure that `-WhatIf` output correctly describes operations which would happen if command was executed without `-WhatIf` switch.</span></span> <span data-ttu-id="e9012-242">Кроме того, убедитесь, что при наличии параметра `–WhatIf` операции не выполняются (не изменяется состояние узла).</span><span class="sxs-lookup"><span data-stu-id="e9012-242">Also, verify that operations does not execute (no changes to the node's state are made) when `–WhatIf` switch is present.</span></span> <span data-ttu-id="e9012-243">Например, предположим, что мы тестируем ресурс File.</span><span class="sxs-lookup"><span data-stu-id="e9012-243">For example, let's assume we are testing File resource.</span></span> <span data-ttu-id="e9012-244">Ниже приведена простая конфигурация, которая создает файл `test.txt` с содержимым test:</span><span class="sxs-lookup"><span data-stu-id="e9012-244">Below is simple configuration which creates file `test.txt` with contents "test":</span></span>

```powershell
configuration config
{
    node localhost
    {
        File file
        {
            Contents="test"
            DestinationPath="C:\test\test.txt"
        }
    }
}
config
```

<span data-ttu-id="e9012-245">Если скомпилировать и выполнить эту конфигурацию с параметром `-WhatIf`, выходные данные сообщают, что именно произойдет при запуске конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e9012-245">If we compile and then execute the configuration with the `-WhatIf` switch, the output is telling us exactly what would happen when we run the configuration.</span></span> <span data-ttu-id="e9012-246">При этом сама конфигурация не выполняется (файл `test.txt` не создается).</span><span class="sxs-lookup"><span data-stu-id="e9012-246">The configuration itself however was not executed (`test.txt` file was not created).</span></span>

```powershell
Start-DscConfiguration -Path .\config -ComputerName localhost -Wait -Verbose -WhatIf
```

```Output
VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer CHARLESX1 with user sid
S-1-5-21-397955417-626881126-188441444-5179871.
What if: [X]: LCM:  [ Start  Set      ]
What if: [X]: LCM:  [ Start  Resource ]  [[File]file]
What if: [X]: LCM:  [ Start  Test     ]  [[File]file]
What if: [X]:                            [[File]file] The system cannot find the file specified.
What if: [X]:                            [[File]file] The related file/directory is: C:\test\test.txt.
What if: [X]: LCM:  [ End    Test     ]  [[File]file]  in 0.0270 seconds.
What if: [X]: LCM:  [ Start  Set      ]  [[File]file]
What if: [X]:                            [[File]file] The system cannot find the file specified.
What if: [X]:                            [[File]file] The related file/directory is: C:\test\test.txt.
What if: [X]:                            [C:\test\test.txt] Creating and writing contents and setting attributes.
What if: [X]: LCM:  [ End    Set      ]  [[File]file]  in 0.0180 seconds.
What if: [X]: LCM:  [ End    Resource ]  [[File]file]
What if: [X]: LCM:  [ End    Set      ]
VERBOSE: [X]: LCM:  [ End    Set      ]    in  0.1050 seconds.
VERBOSE: Operation 'Invoke CimMethod' complete.
```

<span data-ttu-id="e9012-247">Этот список не является исчерпывающим, однако он охватывает множество важных проблем, которые могут возникнуть при проектировании, разработке и тестировании ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="e9012-247">This list is not exhaustive, but it covers many important issues which can be encountered while designing, developing and testing DSC resources.</span></span>
