---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Упаковка и передача ресурсов на опрашиваемый сервер
ms.openlocfilehash: d0e070b7aa43acbbbf087729d53f06dbc7e7734a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782894"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="521e9-103">Упаковка и передача ресурсов на опрашиваемый сервер</span><span class="sxs-lookup"><span data-stu-id="521e9-103">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="521e9-104">В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="521e9-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="521e9-105">Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.</span><span class="sxs-lookup"><span data-stu-id="521e9-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="521e9-106">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="521e9-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="521e9-107">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="521e9-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="521e9-108">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="521e9-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="521e9-109">В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически.</span><span class="sxs-lookup"><span data-stu-id="521e9-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="521e9-110">Когда Узел получает назначенную конфигурацию с помощью команды **получить** или **отправить** (v5), он автоматически загружает любые ресурсы, требуемые конфигурацией, из расположения, указанного в LCM.</span><span class="sxs-lookup"><span data-stu-id="521e9-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="521e9-111">Модули ресурса Package</span><span class="sxs-lookup"><span data-stu-id="521e9-111">Package Resource Modules</span></span>

<span data-ttu-id="521e9-112">Каждый ресурс, доступный клиенту для загрузки, должен храниться в файле `.zip`.</span><span class="sxs-lookup"><span data-stu-id="521e9-112">Each resource available for a client to download must be stored in a `.zip` file.</span></span> <span data-ttu-id="521e9-113">В приведенном ниже примере показаны необходимые шаги с использованием ресурса [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="521e9-113">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="521e9-114">Если у вас есть клиенты, использующие PowerShell 4.0, вам потребуется расширить структуру папок ресурсов и удалить все папки версий.</span><span class="sxs-lookup"><span data-stu-id="521e9-114">If you have any clients using PowerShell 4.0, you will need to flatten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="521e9-115">Дополнительные сведения см. в разделе [Несколько версий ресурса](../configurations/import-dscresource.md#multiple-resource-versions).</span><span class="sxs-lookup"><span data-stu-id="521e9-115">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="521e9-116">Вы можете сжать каталог ресурсов, используя любую программу, сценарий или метод.</span><span class="sxs-lookup"><span data-stu-id="521e9-116">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="521e9-117">В Windows щелкните каталог `xPSDesiredStateConfiguration` _правой кнопкой мыши_ и выберите **Отправить**, а затем — **Сжатая папка**.</span><span class="sxs-lookup"><span data-stu-id="521e9-117">In Windows, you can _right-click_ on the `xPSDesiredStateConfiguration` directory, and select **Send To**, then **Compressed Folder**.</span></span>

![Правый щелчок — "Отправить" — "Сжатая папка"](media/package-upload-resources/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="521e9-119">Именование ресурса Archive</span><span class="sxs-lookup"><span data-stu-id="521e9-119">Naming the Resource Archive</span></span>

<span data-ttu-id="521e9-120">Ресурс Archive должен иметь имя в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="521e9-120">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="521e9-121">В приведенном выше примере `xPSDesiredStateConfiguration.zip` необходимо переименовать в `xPSDesiredStateConfiguration_8.4.4.0.zip`.</span><span class="sxs-lookup"><span data-stu-id="521e9-121">In the example above, `xPSDesiredStateConfiguration.zip` should be renamed `xPSDesiredStateConfiguration_8.4.4.0.zip`.</span></span>

### <a name="create-checksums"></a><span data-ttu-id="521e9-122">Создание контрольных сумм</span><span class="sxs-lookup"><span data-stu-id="521e9-122">Create CheckSums</span></span>

<span data-ttu-id="521e9-123">После сжатия и переименования модуля Resource вам необходимо создать **контрольную сумму**.</span><span class="sxs-lookup"><span data-stu-id="521e9-123">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span> <span data-ttu-id="521e9-124">**Контрольная сумма** используется LCM на клиенте, чтобы определить, был ли изменен ресурс и нужно ли его загрузить снова.</span><span class="sxs-lookup"><span data-stu-id="521e9-124">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="521e9-125">Вы можете создать **контрольную сумму** с помощью командлета [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum), как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="521e9-125">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="521e9-126">Выходные данные не отображаются, но вы увидите xPSDesiredStateConfiguration_8.4.4.0.zip.checksum.</span><span class="sxs-lookup"><span data-stu-id="521e9-126">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="521e9-127">Можно также запустить `New-DSCCheckSum` для каталога файлов с помощью параметра `-Path`.</span><span class="sxs-lookup"><span data-stu-id="521e9-127">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="521e9-128">Если контрольная сумма уже существует, вы можете принудительно создать ее заново с помощью параметра `-Force`.</span><span class="sxs-lookup"><span data-stu-id="521e9-128">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="521e9-129">Где хранить ресурсы Archive</span><span class="sxs-lookup"><span data-stu-id="521e9-129">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="521e9-130">На опрашиваемом HTTP-сервере DSC</span><span class="sxs-lookup"><span data-stu-id="521e9-130">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="521e9-131">Когда вы настраиваете опрашиваемый HTTP-сервер, как описано в статье [Опрашивающая служба Desired State Configuration](pullServer.md), вы указываете ключи для **ModulePath** и **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="521e9-131">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="521e9-132">Ключ **ConfigurationPath** указывает, где должны храниться все MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="521e9-132">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="521e9-133">**ModulePath** указывает, где должны храниться модули ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="521e9-133">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="521e9-134">В общей папке SMB</span><span class="sxs-lookup"><span data-stu-id="521e9-134">On an SMB Share</span></span>

<span data-ttu-id="521e9-135">Если при настройке своего клиента — получателя данных вы указали **ResourceRepositoryShare**, храните архивы и контрольные суммы в каталоге **SourcePath** в блоке **ResourceRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="521e9-135">If you specified a **ResourceRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

<span data-ttu-id="521e9-136">Если при настройке своего клиента — получателя данных вы указали только **ConfigurationRepositoryShare**, храните архивы и контрольные суммы в каталоге **SourcePath** в блоке **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="521e9-136">If you specified only a **ConfigurationRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="521e9-137">Обновление ресурсов</span><span class="sxs-lookup"><span data-stu-id="521e9-137">Updating resources</span></span>

<span data-ttu-id="521e9-138">Вы можете заставить узел обновлять свои ресурсы, изменив номер версии в имени архива или создав новую контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="521e9-138">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="521e9-139">Клиент — получатель данных будет проверять наличие новых версий из необходимых ресурсов, а также обновлять контрольные суммы при обновлении его LCM.</span><span class="sxs-lookup"><span data-stu-id="521e9-139">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="521e9-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="521e9-140">See also</span></span>

- [<span data-ttu-id="521e9-141">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="521e9-141">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="521e9-142">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="521e9-142">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
