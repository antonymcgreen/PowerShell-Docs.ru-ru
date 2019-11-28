---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)
ms.openlocfilehash: 3b094308338e62c783b19f4d3bb41634feee63f6
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417259"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="c40a1-103">Публикация на опрашиваемом сервере с помощью идентификаторов конфигурации (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="c40a1-103">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="c40a1-104">В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="c40a1-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="c40a1-105">Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.</span><span class="sxs-lookup"><span data-stu-id="c40a1-105">If you haven't set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="c40a1-106">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="c40a1-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="c40a1-107">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="c40a1-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="c40a1-108">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="c40a1-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="c40a1-109">В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически.</span><span class="sxs-lookup"><span data-stu-id="c40a1-109">This article shows you how to upload resources so they're available to be downloaded, and configure clients to automatically download resources.</span></span> <span data-ttu-id="c40a1-110">Когда узел получает назначенную конфигурацию с помощью команды **Pull** или **Push** (версия 5), он автоматически загружает любые ресурсы, требуемые для конфигурации, из расположения, указанного в локальном диспетчере конфигураций (LCM)</span><span class="sxs-lookup"><span data-stu-id="c40a1-110">When the node receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the Local Configuration Manager (LCM).</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="c40a1-111">Компиляция конфигураций</span><span class="sxs-lookup"><span data-stu-id="c40a1-111">Compile configurations</span></span>

<span data-ttu-id="c40a1-112">Первый шаг к сохранению [конфигураций](../configurations/configurations.md) на опрашиваемом сервере — скомпилировать их в файлы `.mof`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-112">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into `.mof` files.</span></span> <span data-ttu-id="c40a1-113">Чтобы сделать конфигурацию универсальной и применимой к большему количеству клиентов, используйте `localhost` в блоке узла.</span><span class="sxs-lookup"><span data-stu-id="c40a1-113">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="c40a1-114">В приведенном ниже примере показана оболочка конфигурации, которая использует `localhost` вместо имени конкретного клиента.</span><span class="sxs-lookup"><span data-stu-id="c40a1-114">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="c40a1-115">После компиляции универсальной конфигурации вы должны получить файл `localhost.mof`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-115">Once you've compiled your generic configuration, you should have a `localhost.mof` file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="c40a1-116">Переименование MOF-файла</span><span class="sxs-lookup"><span data-stu-id="c40a1-116">Renaming the MOF file</span></span>

<span data-ttu-id="c40a1-117">Конфигурации файлов `.mof` можно хранить на опрашиваемом сервере, указывая параметр **ConfigurationName** или **ConfigurationID**.</span><span class="sxs-lookup"><span data-stu-id="c40a1-117">You can store Configuration `.mof` files on a Pull Server by **ConfigurationName** or **ConfigurationID**.</span></span> <span data-ttu-id="c40a1-118">В зависимости от того, как вы планируете настроить опрашиваемые клиенты, можно выбрать раздел ниже, чтобы корректно переименовать скомпилированные файлы `.mof`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-118">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled `.mof` files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="c40a1-119">Идентификаторы конфигурации (GUID)</span><span class="sxs-lookup"><span data-stu-id="c40a1-119">Configuration IDs (GUID)</span></span>

<span data-ttu-id="c40a1-120">Вам потребуется переименовать файл `localhost.mof` в `<GUID>.mof`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-120">You'll need to rename your `localhost.mof` file to `<GUID>.mof` file.</span></span> <span data-ttu-id="c40a1-121">Можно создать случайный **GUID** в примере ниже или с помощью командлета [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).</span><span class="sxs-lookup"><span data-stu-id="c40a1-121">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="c40a1-122">Пример вывода</span><span class="sxs-lookup"><span data-stu-id="c40a1-122">Sample Output</span></span>

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="c40a1-123">Затем можно переименовать файл `.mof` любым приемлемым способом.</span><span class="sxs-lookup"><span data-stu-id="c40a1-123">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="c40a1-124">В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="c40a1-124">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="c40a1-125">Дополнительные сведения об использовании **идентификаторов GUID** в вашей среде см. в разделе [Планирование для идентификаторов GUID](/powershell/scripting/dsc/secureserver#guids).</span><span class="sxs-lookup"><span data-stu-id="c40a1-125">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/scripting/dsc/secureserver#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="c40a1-126">Имена файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="c40a1-126">Configuration names</span></span>

<span data-ttu-id="c40a1-127">Вам потребуется переименовать файл `localhost.mof` в `<Configuration Name>.mof`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-127">You'll need to rename your `localhost.mof` file to `<Configuration Name>.mof` file.</span></span> <span data-ttu-id="c40a1-128">В следующем примере используется имя конфигурации из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="c40a1-128">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="c40a1-129">Затем можно переименовать файл `.mof` любым приемлемым способом.</span><span class="sxs-lookup"><span data-stu-id="c40a1-129">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="c40a1-130">В примере ниже используется командлет [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).</span><span class="sxs-lookup"><span data-stu-id="c40a1-130">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="c40a1-131">Создание контрольной суммы</span><span class="sxs-lookup"><span data-stu-id="c40a1-131">Create the checkSum</span></span>

<span data-ttu-id="c40a1-132">С каждым файлом `.mof`, который хранится на опрашиваемом сервере или в общей папке SMB, должен быть связан файл `.checksum`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-132">Each `.mof` file stored on a Pull Server, or SMB share needs to have an associated `.checksum` file.</span></span>
<span data-ttu-id="c40a1-133">Этот файл позволяет клиентам узнать, что связанный файл `.mof` был изменен и должен быть загружен снова.</span><span class="sxs-lookup"><span data-stu-id="c40a1-133">This file lets clients know when the associated `.mof` file has changed and should be downloaded again.</span></span>

<span data-ttu-id="c40a1-134">Вы можете создать **контрольную сумму** с помощью командлета [New-DscChecksum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum).</span><span class="sxs-lookup"><span data-stu-id="c40a1-134">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="c40a1-135">Можно также запустить `New-DSCCheckSum` для каталога файлов с помощью параметра `-Path`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-135">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span>
<span data-ttu-id="c40a1-136">Если контрольная сумма уже существует, вы можете принудительно создать ее заново с помощью параметра `-Force`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-136">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="c40a1-137">В следующем примере указан каталог, которые содержит файл `.mof` из предыдущего раздела, и используется параметр `-Force`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-137">The following example specified a directory containing the `.mof` file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="c40a1-138">Выходные данные не будут отображаться, но теперь должен отобразиться файл `<GUID or Configuration Name>.mof.checksum`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-138">No output will be shown, but you should now see a `<GUID or Configuration Name>.mof.checksum` file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="c40a1-139">Где хранить MOF-файлы и контрольные суммы</span><span class="sxs-lookup"><span data-stu-id="c40a1-139">Where to store MOF files and checkSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="c40a1-140">На опрашиваемом HTTP-сервере DSC</span><span class="sxs-lookup"><span data-stu-id="c40a1-140">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="c40a1-141">Когда вы настраиваете опрашиваемый HTTP-сервер, как описано в статье [Опрашивающая служба Desired State Configuration](pullServer.md), вы указываете ключи для **ModulePath** и **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="c40a1-141">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="c40a1-142">Ключ **ModulePath** указывает, где должны храниться упакованные файлы модуля `.zip`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-142">The **ModulePath** key indicates where a module's packaged `.zip` files should be stored.</span></span> <span data-ttu-id="c40a1-143">Ключ **ConfigurationPath** указывает, где должны храниться все файлы `.mof` и файлы `.checksum`.</span><span class="sxs-lookup"><span data-stu-id="c40a1-143">The **ConfigurationPath** indicates where any `.mof` files and `.checksum` files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="c40a1-144">В общей папке SMB</span><span class="sxs-lookup"><span data-stu-id="c40a1-144">On an SMB share</span></span>

<span data-ttu-id="c40a1-145">При настройке опрашивающего клиента для использования общей папки SMB укажите **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="c40a1-145">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare**.</span></span>
<span data-ttu-id="c40a1-146">Все файлы `.mof` и файлы `.checksum` следует хранить в каталоге **SourcePath** из блока **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="c40a1-146">All `.mof` files and `.checksum` files should be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="c40a1-147">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c40a1-147">Next steps</span></span>

<span data-ttu-id="c40a1-148">Далее необходимо настроить опрашиваемый клиент, чтобы получить конкретную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="c40a1-148">Next, you'll want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="c40a1-149">Дополнительные сведения см. в следующих руководствах.</span><span class="sxs-lookup"><span data-stu-id="c40a1-149">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="c40a1-150">Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="c40a1-150">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="c40a1-151">Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="c40a1-151">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="c40a1-152">Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="c40a1-152">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="c40a1-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="c40a1-153">See also</span></span>

- [<span data-ttu-id="c40a1-154">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="c40a1-154">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="c40a1-155">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="c40a1-155">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="c40a1-156">Упаковка и передача ресурсов на опрашиваемый сервер</span><span class="sxs-lookup"><span data-stu-id="c40a1-156">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
