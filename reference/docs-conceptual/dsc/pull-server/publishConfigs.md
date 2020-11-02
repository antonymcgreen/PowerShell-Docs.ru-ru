---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)
description: В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически.
ms.openlocfilehash: 20e12e3cac6b6e4a86563576f4a915429b18aadb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646841"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="17ea8-104">Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="17ea8-104">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="17ea8-105">В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="17ea8-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="17ea8-106">Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.</span><span class="sxs-lookup"><span data-stu-id="17ea8-106">If you haven't set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="17ea8-107">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="17ea8-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="17ea8-108">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="17ea8-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="17ea8-109">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="17ea8-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="17ea8-110">В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически.</span><span class="sxs-lookup"><span data-stu-id="17ea8-110">This article shows you how to upload resources so they're available to be downloaded, and configure clients to automatically download resources.</span></span> <span data-ttu-id="17ea8-111">Когда узел получает назначенную конфигурацию с помощью команды **Pull** или **Push** (версия 5), он автоматически загружает любые ресурсы, требуемые для конфигурации, из расположения, указанного в локальном диспетчере конфигураций (LCM)</span><span class="sxs-lookup"><span data-stu-id="17ea8-111">When the node receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the Local Configuration Manager (LCM).</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="17ea8-112">Компиляция конфигураций</span><span class="sxs-lookup"><span data-stu-id="17ea8-112">Compile configurations</span></span>

<span data-ttu-id="17ea8-113">Первый шаг к сохранению [конфигураций](../configurations/configurations.md) на опрашиваемом сервере — скомпилировать их в файлы `.mof`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-113">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into `.mof` files.</span></span> <span data-ttu-id="17ea8-114">Чтобы сделать конфигурацию универсальной и применимой к большему количеству клиентов, используйте `localhost` в блоке узла.</span><span class="sxs-lookup"><span data-stu-id="17ea8-114">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="17ea8-115">В приведенном ниже примере показана оболочка конфигурации, которая использует `localhost` вместо имени конкретного клиента.</span><span class="sxs-lookup"><span data-stu-id="17ea8-115">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="17ea8-116">После компиляции универсальной конфигурации вы должны получить файл `localhost.mof`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-116">Once you've compiled your generic configuration, you should have a `localhost.mof` file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="17ea8-117">Переименование MOF-файла</span><span class="sxs-lookup"><span data-stu-id="17ea8-117">Renaming the MOF file</span></span>

<span data-ttu-id="17ea8-118">Конфигурации файлов `.mof` можно хранить на опрашиваемом сервере, указывая параметр **ConfigurationName** или **ConfigurationID** .</span><span class="sxs-lookup"><span data-stu-id="17ea8-118">You can store Configuration `.mof` files on a Pull Server by **ConfigurationName** or **ConfigurationID** .</span></span> <span data-ttu-id="17ea8-119">В зависимости от того, как вы планируете настроить опрашиваемые клиенты, можно выбрать раздел ниже, чтобы корректно переименовать скомпилированные файлы `.mof`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-119">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled `.mof` files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="17ea8-120">Идентификаторы конфигурации (GUID)</span><span class="sxs-lookup"><span data-stu-id="17ea8-120">Configuration IDs (GUID)</span></span>

<span data-ttu-id="17ea8-121">Вам потребуется переименовать файл `localhost.mof` в `<GUID>.mof`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-121">You'll need to rename your `localhost.mof` file to `<GUID>.mof` file.</span></span> <span data-ttu-id="17ea8-122">Можно создать случайный **GUID** в примере ниже или с помощью командлета [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).</span><span class="sxs-lookup"><span data-stu-id="17ea8-122">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="17ea8-123">Пример выходных данных</span><span class="sxs-lookup"><span data-stu-id="17ea8-123">Sample Output</span></span>

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="17ea8-124">Затем можно переименовать файл `.mof` любым приемлемым способом.</span><span class="sxs-lookup"><span data-stu-id="17ea8-124">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="17ea8-125">В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="17ea8-125">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="17ea8-126">Дополнительные сведения об использовании **идентификаторов GUID** в вашей среде см. в разделе [Планирование для идентификаторов GUID](secureServer.md#guids).</span><span class="sxs-lookup"><span data-stu-id="17ea8-126">For more information about using **Guids** in your environment, see [Plan for Guids](secureServer.md#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="17ea8-127">Имена файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="17ea8-127">Configuration names</span></span>

<span data-ttu-id="17ea8-128">Вам потребуется переименовать файл `localhost.mof` в `<Configuration Name>.mof`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-128">You'll need to rename your `localhost.mof` file to `<Configuration Name>.mof` file.</span></span> <span data-ttu-id="17ea8-129">В следующем примере используется имя конфигурации из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="17ea8-129">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="17ea8-130">Затем можно переименовать файл `.mof` любым приемлемым способом.</span><span class="sxs-lookup"><span data-stu-id="17ea8-130">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="17ea8-131">В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="17ea8-131">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="17ea8-132">Создание контрольной суммы</span><span class="sxs-lookup"><span data-stu-id="17ea8-132">Create the checkSum</span></span>

<span data-ttu-id="17ea8-133">С каждым файлом `.mof`, который хранится на опрашиваемом сервере или в общей папке SMB, должен быть связан файл `.checksum`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-133">Each `.mof` file stored on a Pull Server, or SMB share needs to have an associated `.checksum` file.</span></span>
<span data-ttu-id="17ea8-134">Этот файл позволяет клиентам узнать, что связанный файл `.mof` был изменен и должен быть загружен снова.</span><span class="sxs-lookup"><span data-stu-id="17ea8-134">This file lets clients know when the associated `.mof` file has changed and should be downloaded again.</span></span>

<span data-ttu-id="17ea8-135">Вы можете создать **контрольную сумму** с помощью командлета [New-DscChecksum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum).</span><span class="sxs-lookup"><span data-stu-id="17ea8-135">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="17ea8-136">Можно также запустить `New-DSCCheckSum` для каталога файлов с помощью параметра `-Path`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-136">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span>
<span data-ttu-id="17ea8-137">Если контрольная сумма уже существует, вы можете принудительно создать ее заново с помощью параметра `-Force`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-137">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="17ea8-138">В следующем примере указан каталог, которые содержит файл `.mof` из предыдущего раздела, и используется параметр `-Force`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-138">The following example specified a directory containing the `.mof` file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="17ea8-139">Выходные данные не будут отображаться, но теперь должен отобразиться файл `<GUID or Configuration Name>.mof.checksum`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-139">No output will be shown, but you should now see a `<GUID or Configuration Name>.mof.checksum` file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="17ea8-140">Где хранить MOF-файлы и контрольные суммы</span><span class="sxs-lookup"><span data-stu-id="17ea8-140">Where to store MOF files and checkSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="17ea8-141">На опрашиваемом HTTP-сервере DSC</span><span class="sxs-lookup"><span data-stu-id="17ea8-141">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="17ea8-142">Когда вы настраиваете опрашиваемый HTTP-сервер, как описано в статье [Опрашивающая служба Desired State Configuration](pullServer.md), вы указываете ключи для **ModulePath** и **ConfigurationPath** .</span><span class="sxs-lookup"><span data-stu-id="17ea8-142">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="17ea8-143">Ключ **ModulePath** указывает, где должны храниться упакованные файлы модуля `.zip`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-143">The **ModulePath** key indicates where a module's packaged `.zip` files should be stored.</span></span> <span data-ttu-id="17ea8-144">Ключ **ConfigurationPath** указывает, где должны храниться все файлы `.mof` и файлы `.checksum`.</span><span class="sxs-lookup"><span data-stu-id="17ea8-144">The **ConfigurationPath** indicates where any `.mof` files and `.checksum` files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="17ea8-145">В общей папке SMB</span><span class="sxs-lookup"><span data-stu-id="17ea8-145">On an SMB share</span></span>

<span data-ttu-id="17ea8-146">При настройке опрашивающего клиента для использования общей папки SMB укажите **ConfigurationRepositoryShare** .</span><span class="sxs-lookup"><span data-stu-id="17ea8-146">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare** .</span></span>
<span data-ttu-id="17ea8-147">Все файлы `.mof` и файлы `.checksum` следует хранить в каталоге **SourcePath** из блока **ConfigurationRepositoryShare** .</span><span class="sxs-lookup"><span data-stu-id="17ea8-147">All `.mof` files and `.checksum` files should be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="17ea8-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="17ea8-148">Next steps</span></span>

<span data-ttu-id="17ea8-149">Далее необходимо настроить опрашиваемый клиент, чтобы получить конкретную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="17ea8-149">Next, you'll want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="17ea8-150">Дополнительные сведения см. в следующих руководствах.</span><span class="sxs-lookup"><span data-stu-id="17ea8-150">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="17ea8-151">Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="17ea8-151">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="17ea8-152">Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="17ea8-152">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="17ea8-153">Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="17ea8-153">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="17ea8-154">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="17ea8-154">See also</span></span>

- [<span data-ttu-id="17ea8-155">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="17ea8-155">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="17ea8-156">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="17ea8-156">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="17ea8-157">Упаковка и передача ресурсов на опрашиваемый сервер</span><span class="sxs-lookup"><span data-stu-id="17ea8-157">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
