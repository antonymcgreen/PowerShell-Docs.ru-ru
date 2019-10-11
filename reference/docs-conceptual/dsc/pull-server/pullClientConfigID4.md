---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 4.0
ms.openlocfilehash: 9259c624c8725f7d76f61e9ad7caa42e1bfa308c
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955151"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a><span data-ttu-id="bf6b7-103">Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="bf6b7-103">Set up a Pull Client using Configuration IDs in PowerShell 4.0</span></span>

><span data-ttu-id="bf6b7-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="bf6b7-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf6b7-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="bf6b7-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="bf6b7-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="bf6b7-107">Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="bf6b7-108">Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="bf6b7-109">Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="bf6b7-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="bf6b7-110">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="bf6b7-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="bf6b7-111">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="bf6b7-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="bf6b7-112">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="bf6b7-113">В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="bf6b7-114">При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="bf6b7-115">Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="bf6b7-116">Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="bf6b7-117">Настройка LCM опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="bf6b7-117">Configure the pull client LCM</span></span>

<span data-ttu-id="bf6b7-118">После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigID**, в которую будет помещен MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-118">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="bf6b7-119">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-119">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="bf6b7-120">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-120">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="bf6b7-121">Например:</span><span class="sxs-lookup"><span data-stu-id="bf6b7-121">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="bf6b7-122">Идентификатор конфигурации</span><span class="sxs-lookup"><span data-stu-id="bf6b7-122">Configuration ID</span></span>

<span data-ttu-id="bf6b7-123">В следующих примерах свойство **ConfigurationID** LCM заносится в значение **GUID**, которое было создано специально для этой цели.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-123">The examples below set the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="bf6b7-124">Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-124">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="bf6b7-125">MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-125">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="bf6b7-126">Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="bf6b7-126">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="bf6b7-127">Можно создать случайный **GUID**, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-127">You can create a random **Guid** using the example below.</span></span>

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="bf6b7-128">Настройка опрашивающего клиента для скачивания конфигураций</span><span class="sxs-lookup"><span data-stu-id="bf6b7-128">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="bf6b7-129">Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-129">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="bf6b7-130">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-130">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="bf6b7-131">Чтобы настроить LCM, создайте специальный тип конфигурации с помощью блока **LocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-131">To configure the LCM, you create a special type of configuration, with a **LocalConfigurationManager** block.</span></span> <span data-ttu-id="bf6b7-132">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="bf6b7-132">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig4.md).</span></span>

## <a name="http-dsc-pull-server"></a><span data-ttu-id="bf6b7-133">Опрашиваемый сервер DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="bf6b7-133">HTTP DSC Pull Server</span></span>

<span data-ttu-id="bf6b7-134">Если опрашиваемый сервер настроен как веб-служба, задайте параметру **DownloadManagerName** значение **WebDownloadManager**.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-134">If the pull server is set up as a web service, you set the **DownloadManagerName** to **WebDownloadManager**.</span></span> <span data-ttu-id="bf6b7-135">Для параметра **WebDownloadManager** необходимо указать значение **ServerUrl** для ключа **DownloadManagerCustomData**.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-135">The **WebDownloadManager** requires that you specify a **ServerUrl** to the **DownloadManagerCustomData** key.</span></span> <span data-ttu-id="bf6b7-136">Можно также указать значение для **AllowUnsecureConnection**, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-136">You can also specify a value for **AllowUnsecureConnection**, as in the example below.</span></span> <span data-ttu-id="bf6b7-137">Следующий сценарий настраивает LCM для опроса конфигураций с сервера PullServer.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-137">The following script configures the LCM to pull configurations from a server named "PullServer".</span></span>

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
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = "TRUE"}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a><span data-ttu-id="bf6b7-138">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="bf6b7-138">SMB Share</span></span>

<span data-ttu-id="bf6b7-139">Если опрашиваемый сервер настроен как файловый ресурс SMB, а не веб-служба, укажите **DownloadManagerName** для **DscFileDownloadManager**, а не **WebDownLoadManager**.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-139">If the pull server is set up as an SMB file share, rather than a web service, you set the **DownloadManagerName** to **DscFileDownloadManager** rather than the **WebDownLoadManager**.</span></span> <span data-ttu-id="bf6b7-140">Для параметра **DscFileDownloadManager** необходимо указать свойство **SourcePath** в разделе **DownloadManagerCustomData**.</span><span class="sxs-lookup"><span data-stu-id="bf6b7-140">The **DscFileDownloadManager** requires that you specify a **SourcePath** property in the **DownloadManagerCustomData**.</span></span> <span data-ttu-id="bf6b7-141">Следующий сценарий настраивает LCM для опроса конфигураций из общего ресурса SMB "SmbDscShare" на сервере "CONTOSO-SERVER".</span><span class="sxs-lookup"><span data-stu-id="bf6b7-141">The following script configures the LCM to pull configurations from an SMB share named "SmbDscShare" on a server named "CONTOSO-SERVER".</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="bf6b7-142">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="bf6b7-142">Next Steps</span></span>

<span data-ttu-id="bf6b7-143">После настройки опрашивающего клиента можно воспользоваться следующими руководствами для выполнения дальнейших шагов:</span><span class="sxs-lookup"><span data-stu-id="bf6b7-143">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="bf6b7-144">Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)</span><span class="sxs-lookup"><span data-stu-id="bf6b7-144">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="bf6b7-145">Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)</span><span class="sxs-lookup"><span data-stu-id="bf6b7-145">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="bf6b7-146">См. также</span><span class="sxs-lookup"><span data-stu-id="bf6b7-146">See Also</span></span>

- [<span data-ttu-id="bf6b7-147">Опрашивающая служба Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="bf6b7-147">Set up a DSC web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="bf6b7-148">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="bf6b7-148">Set up a DSC SMB pull server</span></span>](pullServerSMB.md)
