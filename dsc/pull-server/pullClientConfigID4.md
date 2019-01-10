---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0
ms.openlocfilehash: 9adc767e91ff19d373c122a0d493e7b8703d5476
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402992"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a><span data-ttu-id="5be50-103">Настройка клиента на включение внесенных изменений с помощью идентификаторы конфигурации в PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="5be50-103">Set up a Pull Client using Configuration IDs in PowerShell 4.0</span></span>

><span data-ttu-id="5be50-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5be50-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5be50-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="5be50-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="5be50-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="5be50-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="5be50-107">Перед настройкой опрашивающего клиента, необходимо настроить опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="5be50-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="5be50-108">На то, что этот порядок не задан, он помогает устранять неполадки и помогает убедиться, что регистрация прошла успешно.</span><span class="sxs-lookup"><span data-stu-id="5be50-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="5be50-109">Чтобы настроить опрашивающий сервер, можно использовать со следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="5be50-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="5be50-110">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="5be50-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="5be50-111">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="5be50-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="5be50-112">Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии.</span><span class="sxs-lookup"><span data-stu-id="5be50-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="5be50-113">В следующих разделах описана настройка опрашивающего клиента с общий ресурс SMB или опрашивающего сервера DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="5be50-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="5be50-114">При обновлении узла LCM, он будет связываться в настроенное расположение для загрузки любого назначенных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="5be50-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="5be50-115">Если все необходимые ресурсы не существуют на узле, он автоматически скачивает их из настроенного расположения.</span><span class="sxs-lookup"><span data-stu-id="5be50-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="5be50-116">Если на узле настраивается с помощью [сервер отчетов](reportServer.md), затем он сообщит состояние операции.</span><span class="sxs-lookup"><span data-stu-id="5be50-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="5be50-117">Настройка опрашивающего клиента LCM</span><span class="sxs-lookup"><span data-stu-id="5be50-117">Configure the pull client LCM</span></span>

<span data-ttu-id="5be50-118">Выполнение любой из приведенных ниже примерах создается новая выходная папка с именем **PullClientConfigID** и MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="5be50-118">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="5be50-119">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="5be50-119">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="5be50-120">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="5be50-120">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="5be50-121">Например:</span><span class="sxs-lookup"><span data-stu-id="5be50-121">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="5be50-122">Идентификатор конфигурации</span><span class="sxs-lookup"><span data-stu-id="5be50-122">Configuration ID</span></span>

<span data-ttu-id="5be50-123">В примерах ниже набор **ConfigurationID** в lcm на **Guid** , было создано для этой цели.</span><span class="sxs-lookup"><span data-stu-id="5be50-123">The examples below set the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="5be50-124">Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="5be50-124">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="5be50-125">MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла.</span><span class="sxs-lookup"><span data-stu-id="5be50-125">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="5be50-126">Дополнительные сведения см. в разделе [конфигураций публикации опрашивающий сервер (v4/v5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="5be50-126">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="5be50-127">Можно создать случайный **Guid** в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="5be50-127">You can create a random **Guid** using the example below.</span></span>

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="5be50-128">Настройка клиента на включение внесенных изменений для загрузки конфигураций</span><span class="sxs-lookup"><span data-stu-id="5be50-128">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="5be50-129">Каждый клиент должен быть настроен в **по запросу** режима и URL-адрес сервера по запросу хранения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5be50-129">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="5be50-130">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="5be50-130">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="5be50-131">Чтобы настроить LCM, создайте специальный тип конфигурации, с **LocalConfigurationManager** блока.</span><span class="sxs-lookup"><span data-stu-id="5be50-131">To configure the LCM, you create a special type of configuration, with a **LocalConfigurationManager** block.</span></span> <span data-ttu-id="5be50-132">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="5be50-132">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig4.md).</span></span>

## <a name="http-dsc-pull-server"></a><span data-ttu-id="5be50-133">DSC опрашивающий HTTP-сервер</span><span class="sxs-lookup"><span data-stu-id="5be50-133">HTTP DSC Pull Server</span></span>

<span data-ttu-id="5be50-134">Если опрашивающий сервер настроен как веб-службы, задать **DownloadManagerName** для **WebDownloadManager**.</span><span class="sxs-lookup"><span data-stu-id="5be50-134">If the pull server is set up as a web service, you set the **DownloadManagerName** to **WebDownloadManager**.</span></span> <span data-ttu-id="5be50-135">**WebDownloadManager** необходимо указать **ServerUrl** для **DownloadManagerCustomData** ключ.</span><span class="sxs-lookup"><span data-stu-id="5be50-135">The **WebDownloadManager** requires that you specify a **ServerUrl** to the **DownloadManagerCustomData** key.</span></span> <span data-ttu-id="5be50-136">Можно также указать значение для **AllowUnsecureConnection**, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="5be50-136">You can also specify a value for **AllowUnsecureConnection**, as in the example below.</span></span> <span data-ttu-id="5be50-137">Следующий сценарий настраивает LCM для опроса конфигураций с сервера PullServer.</span><span class="sxs-lookup"><span data-stu-id="5be50-137">The following script configures the LCM to pull configurations from a server named "PullServer".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a><span data-ttu-id="5be50-138">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="5be50-138">SMB Share</span></span>

<span data-ttu-id="5be50-139">Если опрашивающий сервер настроен как файловый ресурс SMB, а не веб-службы, задать **DownloadManagerName** для **DscFileDownloadManager** вместо **WebDownLoadManager**.</span><span class="sxs-lookup"><span data-stu-id="5be50-139">If the pull server is set up as an SMB file share, rather than a web service, you set the **DownloadManagerName** to **DscFileDownloadManager** rather than the **WebDownLoadManager**.</span></span> <span data-ttu-id="5be50-140">**DscFileDownloadManager** необходимо указать **SourcePath** свойство в **DownloadManagerCustomData**.</span><span class="sxs-lookup"><span data-stu-id="5be50-140">The **DscFileDownloadManager** requires that you specify a **SourcePath** property in the **DownloadManagerCustomData**.</span></span> <span data-ttu-id="5be50-141">Следующий сценарий настраивает LCM для опроса конфигураций из общего ресурса SMB "SmbDscShare" на сервере "CONTOSO-SERVER".</span><span class="sxs-lookup"><span data-stu-id="5be50-141">The following script configures the LCM to pull configurations from an SMB share named "SmbDscShare" on a server named "CONTOSO-SERVER".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
PullClientConfigId -Output "."
```

## <a name="next-steps"></a><span data-ttu-id="5be50-142">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5be50-142">Next Steps</span></span>

<span data-ttu-id="5be50-143">После настройки опрашивающий клиент, можно использовать со следующими руководствами для выполните следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="5be50-143">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="5be50-144">Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)</span><span class="sxs-lookup"><span data-stu-id="5be50-144">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="5be50-145">Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)</span><span class="sxs-lookup"><span data-stu-id="5be50-145">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="5be50-146">См. также</span><span class="sxs-lookup"><span data-stu-id="5be50-146">See Also</span></span>

- [<span data-ttu-id="5be50-147">Настройка опрашивающего веб-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="5be50-147">Set up a DSC web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="5be50-148">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="5be50-148">Set up a DSC SMB pull server</span></span>](pullServerSMB.md)
