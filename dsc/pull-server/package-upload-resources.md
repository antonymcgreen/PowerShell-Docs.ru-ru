---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Пакет и ресурсы передачи к опрашивающему серверу
ms.openlocfilehash: 29a62f96393a53c9e7da57a5e51732dcb0937194
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402299"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a><span data-ttu-id="3ab3e-103">Пакет и ресурсы передачи к опрашивающему серверу</span><span class="sxs-lookup"><span data-stu-id="3ab3e-103">Package and Upload Resources to a Pull Server</span></span>

<span data-ttu-id="3ab3e-104">В следующих разделах предполагается, что вы уже настроили опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="3ab3e-105">Если ваш сервер на включение внесенных изменений не установлен, можно использовать со следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="3ab3e-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="3ab3e-106">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="3ab3e-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="3ab3e-107">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="3ab3e-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="3ab3e-108">Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="3ab3e-109">В этой статье показано, как передать ресурсы, чтобы они были доступны, которые требуется загрузить и настроить клиенты для загрузки ресурсов автоматически.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="3ab3e-110">Когда узел получает назначенной конфигурации, с помощью **на включение внесенных изменений** или **Push** (v5), он автоматически скачивает все ресурсы, требования конфигурации из местоположения, указанного в LCM.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="package-resource-modules"></a><span data-ttu-id="3ab3e-111">Модули ресурсов пакета</span><span class="sxs-lookup"><span data-stu-id="3ab3e-111">Package Resource Modules</span></span>

<span data-ttu-id="3ab3e-112">Каждый ресурс, доступный для клиента для загрузки должен храниться в файл «ZIP».</span><span class="sxs-lookup"><span data-stu-id="3ab3e-112">Each resource available for a client to download must be stored in a ".zip" file.</span></span> <span data-ttu-id="3ab3e-113">В приведенном ниже примере отображается с помощью действия, необходимые [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-113">The example below will show the required steps using the [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0) resource.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab3e-114">При наличии любых клиентов, с помощью PowerShell 4.0, будет необходимо flaten структуру папки ресурсов и удалите все версии папки.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-114">If you have any clients using PowerShell 4.0, you will need to flaten the resource folder structure and remove any version folders.</span></span> <span data-ttu-id="3ab3e-115">Дополнительные сведения см. в разделе [нескольких версий ресурса](../configurations/import-dscresource.md#multiple-resource-versions).</span><span class="sxs-lookup"><span data-stu-id="3ab3e-115">For more information, see [Multiple Resource Versions](../configurations/import-dscresource.md#multiple-resource-versions).</span></span>

<span data-ttu-id="3ab3e-116">Каталог ресурсов, с помощью любой служебной программы, скрипт или метод, который вы предпочитаете, можно сжать.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-116">You can compress the resource directory using any utility, script, or method that you prefer.</span></span> <span data-ttu-id="3ab3e-117">В Windows, вы можете *щелкните правой кнопкой мыши* каталог «xPSDesiredStateConfiguration», и выберите «Отправить», а затем «Сжатую папку».</span><span class="sxs-lookup"><span data-stu-id="3ab3e-117">In Windows, you can *right-click* on the "xPSDesiredStateConfiguration" directory, and select "Send To", then "Compressed Folder".</span></span>

![Щелчок правой кнопкой мыши](../media/right-click.gif)

### <a name="naming-the-resource-archive"></a><span data-ttu-id="3ab3e-119">Именование ресурсов архива</span><span class="sxs-lookup"><span data-stu-id="3ab3e-119">Naming the Resource Archive</span></span>

<span data-ttu-id="3ab3e-120">Архив ресурса должен иметь имя в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="3ab3e-120">The Resource archive needs to be named with the following format:</span></span>

```
{ModuleName}_{Version}.zip
```

<span data-ttu-id="3ab3e-121">В приведенном выше примере «xPSDesiredStateConfiguration.zip» должен быть переименован «xPSDesiredStateConfiguration_8.4.4.0.zip».</span><span class="sxs-lookup"><span data-stu-id="3ab3e-121">In the example above, "xPSDesiredStateConfiguration.zip" should be renamed "xPSDesiredStateConfiguration_8.4.4.0.zip".</span></span>

### <a name="create-checksums"></a><span data-ttu-id="3ab3e-122">Создание контрольных сумм</span><span class="sxs-lookup"><span data-stu-id="3ab3e-122">Create CheckSums</span></span>

<span data-ttu-id="3ab3e-123">После модуля ресурсов были сжаты и переименован, необходимо создать **контрольной суммы**.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-123">Once the Resource module has been compressed and renamed, you need to create a **CheckSum**.</span></span>  <span data-ttu-id="3ab3e-124">**Контрольной суммы** используется, LCM на клиенте, чтобы определить, если ресурс был изменен и должен быть загружен снова.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-124">The **CheckSum** is used, by the LCM on the client, to determine if the resource has been changed, and needs to be downloaded again.</span></span> <span data-ttu-id="3ab3e-125">Можно создать **контрольной суммы** с [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) командлет, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-125">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet, as shown in the example below.</span></span>

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

<span data-ttu-id="3ab3e-126">Выходные данные не отображаются, но теперь вы увидите «xPSDesiredStateConfiguration_8.4.4.0.zip.checksum».</span><span class="sxs-lookup"><span data-stu-id="3ab3e-126">No output will be shown, but you should now see a "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum".</span></span> <span data-ttu-id="3ab3e-127">Можно также запустить `New-DSCCheckSum` от каталога с файлами с помощью `-Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-127">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span> <span data-ttu-id="3ab3e-128">Если контрольная сумма уже существует, можно будет применить его повторного создания с `-Force` параметра.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-128">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span>

### <a name="where-to-store-resource-archives"></a><span data-ttu-id="3ab3e-129">Где хранить архивы ресурсов</span><span class="sxs-lookup"><span data-stu-id="3ab3e-129">Where to store Resource Archives</span></span>

#### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="3ab3e-130">На HTTP опрашивающего сервера DSC</span><span class="sxs-lookup"><span data-stu-id="3ab3e-130">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="3ab3e-131">При настройке сервера по запросу HTTP, как описано в [Настройка опрашивающего сервера DSC HTTP](pullServer.md), укажите каталоги для **ModulePath** и **ConfigurationPath** ключи.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-131">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="3ab3e-132">**ConfigurationPath** ключ указывает, где должны храниться все MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-132">The **ConfigurationPath** key indicates where any ".mof" files should be stored.</span></span> <span data-ttu-id="3ab3e-133">**ModulePath** указывает, где должно храниться модули ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-133">The **ModulePath** indicates where any DSC Resource Modules should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a><span data-ttu-id="3ab3e-134">В общем ресурсе SMB</span><span class="sxs-lookup"><span data-stu-id="3ab3e-134">On an SMB Share</span></span>

<span data-ttu-id="3ab3e-135">Если вы указали **ResourceRepositoryShare**, при настройке клиента на включение внесенных изменений, хранить архивы и контрольные суммы в **SourcePath** каталог из **ResourceRepositoryShare** блока.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-135">If you specified a **ResourceRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ResourceRepositoryShare** block.</span></span>

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

<span data-ttu-id="3ab3e-136">Если вы указали только **ConfigurationRepositoryShare**, при настройке клиента на включение внесенных изменений, хранить архивы и контрольные суммы в **SourcePath** каталог из  **ConfigurationRepositoryShare** блока.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-136">If you specified only a **ConfigurationRepositoryShare**, when setting up your Pull Client, store archives and checksums in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a><span data-ttu-id="3ab3e-137">Обновление ресурсов</span><span class="sxs-lookup"><span data-stu-id="3ab3e-137">Updating resources</span></span>

<span data-ttu-id="3ab3e-138">Вы можете принудительно узла для обновления ресурсов путем изменения номера версии в имя архива или путем создания новой контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-138">You can force a Node to update its resources by changing the version number in the archive's name, or by creating a new checksum.</span></span> <span data-ttu-id="3ab3e-139">Опрашивающий клиент будет проверять наличие новых версий из необходимых ресурсов, а также обновляется контрольные суммы, в том случае, когда обновляет его LCM.</span><span class="sxs-lookup"><span data-stu-id="3ab3e-139">The Pull Client will check for newer versions of required resources, as well as updated checksums, when its LCM refreshes.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ab3e-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="3ab3e-140">See also</span></span>

- [<span data-ttu-id="3ab3e-141">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="3ab3e-141">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="3ab3e-142">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="3ab3e-142">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
