---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Публикация опрашивающий сервер, используя идентификаторы конфигурации (v4/v5)
ms.openlocfilehash: 0144fec43d7a8d65b79891567cc0dc3952175343
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402400"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="dca00-103">Публикация опрашивающий сервер, используя идентификаторы конфигурации (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="dca00-103">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="dca00-104">В следующих разделах предполагается, что вы уже настроили опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="dca00-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="dca00-105">Если ваш сервер на включение внесенных изменений не установлен, можно использовать со следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="dca00-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="dca00-106">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="dca00-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="dca00-107">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="dca00-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="dca00-108">Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии.</span><span class="sxs-lookup"><span data-stu-id="dca00-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="dca00-109">В этой статье показано, как передать ресурсы, чтобы они были доступны, которые требуется загрузить и настроить клиенты для загрузки ресурсов автоматически.</span><span class="sxs-lookup"><span data-stu-id="dca00-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="dca00-110">Когда узел получает назначенной конфигурации, с помощью **на включение внесенных изменений** или **Push** (v5), он автоматически скачивает все ресурсы, требования конфигурации из местоположения, указанного в LCM.</span><span class="sxs-lookup"><span data-stu-id="dca00-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="dca00-111">Компилировать конфигурации</span><span class="sxs-lookup"><span data-stu-id="dca00-111">Compile Configurations</span></span>

<span data-ttu-id="dca00-112">Первым шагом к хранению [конфигураций](../configurations/configurations.md) на опрашивающем сервере — скомпилировать их в MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="dca00-112">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into ".mof" files.</span></span> <span data-ttu-id="dca00-113">Чтобы сделать конфигурацию универсальных и применимые на большее количество клиентов, используйте `localhost` в блок узла.</span><span class="sxs-lookup"><span data-stu-id="dca00-113">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="dca00-114">В приведенном ниже примере показано оболочку настройки, который использует `localhost` вместо имени конкретного клиента.</span><span class="sxs-lookup"><span data-stu-id="dca00-114">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="dca00-115">После компиляции конфигурацию универсального должны иметь файл «localhost.mof».</span><span class="sxs-lookup"><span data-stu-id="dca00-115">Once you have compiled your generic configuration, you should have a "localhost.mof" file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="dca00-116">Переименование MOF-файл</span><span class="sxs-lookup"><span data-stu-id="dca00-116">Renaming the MOF file</span></span>

<span data-ttu-id="dca00-117">Можно хранить «MOF-файлы конфигурации на опрашивающем сервере с **ConfigurationName** или **ConfigurationID**.</span><span class="sxs-lookup"><span data-stu-id="dca00-117">You can store Configuration ".mof" files on a Pull Server by **ConfigurationName** or **ConfigurationID**.</span></span> <span data-ttu-id="dca00-118">В зависимости от того, как вы планируете настроить клиенты на включение внесенных изменений можно выбрать раздел для должным образом переименовать ваш скомпилированный MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="dca00-118">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled ".mof" files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="dca00-119">Конфигурация идентификаторы (GUID)</span><span class="sxs-lookup"><span data-stu-id="dca00-119">Configuration IDs (GUID)</span></span>

<span data-ttu-id="dca00-120">Необходимо будет переименовать файл «localhost.mof» для "<GUID>.mof» файла.</span><span class="sxs-lookup"><span data-stu-id="dca00-120">You will need to rename your "localhost.mof" file to "<GUID>.mof" file.</span></span> <span data-ttu-id="dca00-121">Можно создать случайный **Guid** в примере ниже, или с помощью [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) командлета.</span><span class="sxs-lookup"><span data-stu-id="dca00-121">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="dca00-122">Пример вывода</span><span class="sxs-lookup"><span data-stu-id="dca00-122">Sample Output</span></span>

```output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="dca00-123">Затем можно ввести имя файла «.mof» любым приемлемым способом.</span><span class="sxs-lookup"><span data-stu-id="dca00-123">You can then rename your ".mof" file using any acceptable method.</span></span> <span data-ttu-id="dca00-124">В примере ниже используется [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) командлета.</span><span class="sxs-lookup"><span data-stu-id="dca00-124">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="dca00-125">Дополнительные сведения об использовании **идентификаторы GUID** в вашей среде, см. в разделе [планирование идентификаторы GUID](/powershell/dsc/secureserver#guids).</span><span class="sxs-lookup"><span data-stu-id="dca00-125">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/dsc/secureserver#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="dca00-126">Имена параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="dca00-126">Configuration Names</span></span>

<span data-ttu-id="dca00-127">Необходимо будет переименовать файл «localhost.mof» для "<Configuration Name>.mof» файла.</span><span class="sxs-lookup"><span data-stu-id="dca00-127">You will need to rename your "localhost.mof" file to "<Configuration Name>.mof" file.</span></span> <span data-ttu-id="dca00-128">В следующем примере используется имя конфигурации из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="dca00-128">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="dca00-129">Затем можно ввести имя файла «.mof» любым приемлемым способом.</span><span class="sxs-lookup"><span data-stu-id="dca00-129">You can then rename your ".mof" file using any acceptable method.</span></span> <span data-ttu-id="dca00-130">В примере ниже используется [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) командлета.</span><span class="sxs-lookup"><span data-stu-id="dca00-130">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="dca00-131">Создать контрольную сумму</span><span class="sxs-lookup"><span data-stu-id="dca00-131">Create the CheckSum</span></span>

<span data-ttu-id="dca00-132">Каждый файл «.mof» хранятся на опрашивающий сервер или общий ресурс SMB должен быть файлом связанный «.checksum».</span><span class="sxs-lookup"><span data-stu-id="dca00-132">Each ".mof" file stored on a Pull Server, or SMB share needs to have an associated ".checksum" file.</span></span> <span data-ttu-id="dca00-133">Этот файл позволяет клиентам узнать, когда связанный MOF «-» файл был изменен и должен загружаться снова.</span><span class="sxs-lookup"><span data-stu-id="dca00-133">This file lets clients know when the associated ".mof" file has changed and should be downloaded again.</span></span>

<span data-ttu-id="dca00-134">Можно создать **контрольной суммы** с [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) командлета.</span><span class="sxs-lookup"><span data-stu-id="dca00-134">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="dca00-135">Можно также запустить `New-DSCCheckSum` от каталога с файлами с помощью `-Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="dca00-135">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="dca00-136">Если контрольная сумма уже существует, можно будет применить его повторного создания с `-Force` параметра.</span><span class="sxs-lookup"><span data-stu-id="dca00-136">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="dca00-137">В следующем примере указан каталог, содержащий файл «.mof» из предыдущего раздела и использует `-Force` параметра.</span><span class="sxs-lookup"><span data-stu-id="dca00-137">The following example specified a directory containing the ".mof" file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="dca00-138">Выходные данные не отображаются, но теперь вы увидите "<GUID or Configuration Name>. mof.checksum» файла.</span><span class="sxs-lookup"><span data-stu-id="dca00-138">No output will be shown, but you should now see a "<GUID or Configuration Name>.mof.checksum" file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="dca00-139">Где хранить файлы MOF и контрольные суммы</span><span class="sxs-lookup"><span data-stu-id="dca00-139">Where to store MOF files and CheckSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="dca00-140">На HTTP опрашивающего сервера DSC</span><span class="sxs-lookup"><span data-stu-id="dca00-140">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="dca00-141">При настройке сервера по запросу HTTP, как описано в [Настройка опрашивающего сервера DSC HTTP](pullServer.md), укажите каталоги для **ModulePath** и **ConfigurationPath** ключи.</span><span class="sxs-lookup"><span data-stu-id="dca00-141">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="dca00-142">**ConfigurationPath** ключ указывает, где должны храниться все MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="dca00-142">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="dca00-143">**ConfigurationPath** указывает, где должны храниться все MOF-файлы и файлы «.checksum».</span><span class="sxs-lookup"><span data-stu-id="dca00-143">The **ConfigurationPath** indicates where any ".mof" files and ".checksum" files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="dca00-144">В общем ресурсе SMB</span><span class="sxs-lookup"><span data-stu-id="dca00-144">On an SMB Share</span></span>

<span data-ttu-id="dca00-145">При настройке опрашивающий клиент использовать общую папку SMB, укажите **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="dca00-145">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="dca00-146">Все MOF-файлы и файлы «.checksum» следует хранить в **SourcePath** каталог из **ConfigurationRepositoryShare** блока.</span><span class="sxs-lookup"><span data-stu-id="dca00-146">All ".mof" files and ".checksum" files should then be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="dca00-147">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="dca00-147">Next Steps</span></span>

<span data-ttu-id="dca00-148">Далее необходимо настроить на клиентах по запросу на включение внесенных изменений указанной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dca00-148">Next, you will want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="dca00-149">Дополнительные сведения см. в одном из следующих руководств:</span><span class="sxs-lookup"><span data-stu-id="dca00-149">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="dca00-150">Настройте опрашивающий клиент, используя идентификаторы конфигурации (версия 4)</span><span class="sxs-lookup"><span data-stu-id="dca00-150">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="dca00-151">Настройте опрашивающий клиент, используя идентификаторы конфигурации (v5)</span><span class="sxs-lookup"><span data-stu-id="dca00-151">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="dca00-152">Настройка клиента на включение внесенных изменений с помощью имен конфигураций (v5)</span><span class="sxs-lookup"><span data-stu-id="dca00-152">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="dca00-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="dca00-153">See also</span></span>

- [<span data-ttu-id="dca00-154">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="dca00-154">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="dca00-155">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="dca00-155">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="dca00-156">Пакет и ресурсы передачи к опрашивающему серверу</span><span class="sxs-lookup"><span data-stu-id="dca00-156">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
