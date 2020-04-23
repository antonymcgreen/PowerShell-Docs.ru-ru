---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше
ms.openlocfilehash: a014e04fc5fbf2e813d9b0d79f39fe5aa3836f86
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500732"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a><span data-ttu-id="8cf71-103">Настройка опрашивающего клиента с помощью идентификаторов конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="8cf71-103">Set up a Pull Client using Configuration IDs in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="8cf71-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8cf71-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cf71-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="8cf71-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="8cf71-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="8cf71-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="8cf71-107">Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="8cf71-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="8cf71-108">Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно.</span><span class="sxs-lookup"><span data-stu-id="8cf71-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="8cf71-109">Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="8cf71-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="8cf71-110">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="8cf71-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="8cf71-111">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="8cf71-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="8cf71-112">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="8cf71-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="8cf71-113">В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="8cf71-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="8cf71-114">При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="8cf71-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="8cf71-115">Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения.</span><span class="sxs-lookup"><span data-stu-id="8cf71-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="8cf71-116">Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.</span><span class="sxs-lookup"><span data-stu-id="8cf71-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf71-117">Этот раздел относится к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="8cf71-117">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="8cf71-118">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="8cf71-118">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="8cf71-119">Настройка LCM опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="8cf71-119">Configure the pull client LCM</span></span>

<span data-ttu-id="8cf71-120">После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigID**, в которую будет помещен MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="8cf71-120">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="8cf71-121">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="8cf71-121">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="8cf71-122">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="8cf71-122">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="8cf71-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="8cf71-123">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="8cf71-124">Идентификатор конфигурации</span><span class="sxs-lookup"><span data-stu-id="8cf71-124">Configuration ID</span></span>

<span data-ttu-id="8cf71-125">Примеры ниже заносят в свойство **ConfigurationID** LCM значение **GUID**, которое было создано специально для этой цели.</span><span class="sxs-lookup"><span data-stu-id="8cf71-125">The examples below sets the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="8cf71-126">Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="8cf71-126">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="8cf71-127">MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла.</span><span class="sxs-lookup"><span data-stu-id="8cf71-127">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="8cf71-128">Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="8cf71-128">For more information see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="8cf71-129">Можно создать случайный **GUID** в примере ниже или с помощью командлета [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).</span><span class="sxs-lookup"><span data-stu-id="8cf71-129">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="8cf71-130">Дополнительные сведения об использовании **идентификаторов GUID** в вашей среде см. в разделе [Планирование для идентификаторов GUID](secureserver.md#guids).</span><span class="sxs-lookup"><span data-stu-id="8cf71-130">For more information about using **Guids** in your environment, see [Plan for Guids](secureserver.md#guids).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="8cf71-131">Настройка опрашивающего клиента для скачивания конфигураций</span><span class="sxs-lookup"><span data-stu-id="8cf71-131">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="8cf71-132">Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8cf71-132">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="8cf71-133">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="8cf71-133">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="8cf71-134">Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-134">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="8cf71-135">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="8cf71-135">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="8cf71-136">Опрашиваемый сервер DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="8cf71-136">HTTP DSC Pull Server</span></span>

<span data-ttu-id="8cf71-137">Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.</span><span class="sxs-lookup"><span data-stu-id="8cf71-137">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }
    }
}
PullClientConfigID
```

<span data-ttu-id="8cf71-138">В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="8cf71-138">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="8cf71-139">**ServerUrl** указывает URL-адрес опрашиваемого сервера DSC.</span><span class="sxs-lookup"><span data-stu-id="8cf71-139">The **ServerUrl** specifies the url of the DSC Pull</span></span>

### <a name="smb-share"></a><span data-ttu-id="8cf71-140">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="8cf71-140">SMB Share</span></span>

<span data-ttu-id="8cf71-141">Следующий сценарий настраивает LCM для опроса конфигураций с общего ресурса SMB с именем `\\SMBPullServer\Pull`.</span><span class="sxs-lookup"><span data-stu-id="8cf71-141">The following script configures the LCM to pull configurations from the SMB Share `\\SMBPullServer\Pull`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Pull'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="8cf71-142">В скрипте блок **ConfigurationRepositoryShare** задает опрашиваемый сервер, которым в этом случае является общий ресурс SMB.</span><span class="sxs-lookup"><span data-stu-id="8cf71-142">In the script, the **ConfigurationRepositoryShare** block defines the pull server, which in this case, is just an SMB share.</span></span>

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="8cf71-143">Настройка опрашивающего клиента для скачивания ресурсов</span><span class="sxs-lookup"><span data-stu-id="8cf71-143">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="8cf71-144">Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы оттуда же, откуда и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8cf71-144">If you specify only the **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous examples), the pull client will pull resources from the same location it retrieves its configurations.</span></span> <span data-ttu-id="8cf71-145">Можно также указать различные расположения для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8cf71-145">You can also specify separate locations for resources.</span></span> <span data-ttu-id="8cf71-146">Чтобы указать расположение ресурсов как отдельный сервер, используйте блок **ResourceRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-146">To specify a resource location as a separate server, use the **ResourceRepositoryWeb** block.</span></span> <span data-ttu-id="8cf71-147">Чтобы указать расположение ресурсов как общий ресурс SMB, используйте блок **ResourceRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-147">To specify a resource location as an SMB share, use the **ResourceRepositoryShare** block.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf71-148">Вы можете объединить **ConfigurationRepositoryWeb** с **ResourceRepositoryShare** или **ConfigurationRepositoryShare** с **ResourceRepositoryWeb** .</span><span class="sxs-lookup"><span data-stu-id="8cf71-148">You can combine **ConfigurationRepositoryWeb** with **ResourceRepositoryShare** or **ConfigurationRepositoryShare** with **ResourceRepositoryWeb**.</span></span> <span data-ttu-id="8cf71-149">Примеров этого ниже нет.</span><span class="sxs-lookup"><span data-stu-id="8cf71-149">Examples of this are not shown below.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="8cf71-150">Опрашиваемый сервер DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="8cf71-150">HTTP DSC Pull Server</span></span>

<span data-ttu-id="8cf71-151">Следующая метаконфигурация настраивает опрашивающий клиент для получения конфигураций из **CONTOSO-PullSrv** и ресурсов из **CONTOSO-ResourceSrv**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-151">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="8cf71-152">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="8cf71-152">SMB Share</span></span>

<span data-ttu-id="8cf71-153">В следующем примере показана метаконфигурация, которая настраивает клиент для получения конфигураций с общего ресурса SMB `\\SMBPullServer\Configurations`, а ресурсов — с общего ресурса SMB `\\SMBPullServer\Resources`.</span><span class="sxs-lookup"><span data-stu-id="8cf71-153">The following example shows a metaconfiguration that sets up a client to pull configurations from the SMB share `\\SMBPullServer\Configurations`, and resources from the SMB share `\\SMBPullServer\Resources`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Configurations'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

#### <a name="automatically-download-resources-in-push-mode"></a><span data-ttu-id="8cf71-154">Автоматическое скачивание ресурсов в режиме Push</span><span class="sxs-lookup"><span data-stu-id="8cf71-154">Automatically download Resources in Push Mode</span></span>

<span data-ttu-id="8cf71-155">Начиная с PowerShell 5.0 опрашивающие клиенты могут скачивать модули из общего ресурса SMB даже в том случае, если они настроены в режиме **Push**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-155">Beginning in PowerShell 5.0, your pull clients can download modules from an SMB share, even when they are configured for **Push** mode.</span></span> <span data-ttu-id="8cf71-156">Это особенно полезно в сценариях, когда вы не хотите настраивать опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="8cf71-156">This is especially useful in scenarios where you do not want to set up a Pull Server.</span></span> <span data-ttu-id="8cf71-157">Блок **ResourceRepositoryShare** может использоваться без указания **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-157">The **ResourceRepositoryShare** block can be used without specifying a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="8cf71-158">В следующем примере показана метаконфигурация, которая настраивает клиент для получения ресурсов с общего ресурса SMB `\\SMBPullServer\Resources`.</span><span class="sxs-lookup"><span data-stu-id="8cf71-158">The following example shows a metaconfiguration that sets up a client to pull resources from an SMB Share `\\SMBPullServer\Resources`.</span></span> <span data-ttu-id="8cf71-159">Когда на узел принудительно **отправляется** конфигурация, он автоматически скачивает все необходимые ресурсы с указанного общего ресурса.</span><span class="sxs-lookup"><span data-stu-id="8cf71-159">When the Node is **PUSHED** a configuration, it will automatically download any required resources, from the share specified.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Push'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="8cf71-160">Настройка опрашивающего клиента для отчета о состоянии</span><span class="sxs-lookup"><span data-stu-id="8cf71-160">Set up a Pull Client to report status</span></span>

<span data-ttu-id="8cf71-161">По умолчанию узлы не отправляют отчеты на настроенный опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="8cf71-161">By default, Nodes will not send reports to a configured Pull Server.</span></span> <span data-ttu-id="8cf71-162">Можно использовать один и тот же опрашивающий сервер для конфигураций, ресурсов и создания отчетов, но необходимо создать блок **ReportRepositoryWeb** для настройки отчетов.</span><span class="sxs-lookup"><span data-stu-id="8cf71-162">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="8cf71-163">Опрашиваемый сервер DSC HTTP</span><span class="sxs-lookup"><span data-stu-id="8cf71-163">HTTP DSC Pull Server</span></span>

<span data-ttu-id="8cf71-164">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="8cf71-164">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="8cf71-165">Чтобы указать сервер отчетов, используйте блок **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-165">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="8cf71-166">Сервер отчетов не может быть SMB-сервером.</span><span class="sxs-lookup"><span data-stu-id="8cf71-166">A report server cannot be an SMB server.</span></span> <span data-ttu-id="8cf71-167">Следующая метаконфигурация настраивает для опрашивающего клиента получение конфигураций с **CONTOSO-PullSrv**, ресурсов — с **CONTOSO-ResourceSrv**, а также отправку отчетов о состоянии на **CONTOSO-ReportSrv**.</span><span class="sxs-lookup"><span data-stu-id="8cf71-167">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="8cf71-168">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="8cf71-168">SMB Share</span></span>

<span data-ttu-id="8cf71-169">Сервер отчетов не может быть общим ресурсом SMB.</span><span class="sxs-lookup"><span data-stu-id="8cf71-169">A report server cannot be an SMB share.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8cf71-170">Next Steps</span><span class="sxs-lookup"><span data-stu-id="8cf71-170">Next Steps</span></span>

<span data-ttu-id="8cf71-171">После настройки опрашивающего клиента можно воспользоваться следующими руководствами для выполнения дальнейших шагов:</span><span class="sxs-lookup"><span data-stu-id="8cf71-171">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="8cf71-172">Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)</span><span class="sxs-lookup"><span data-stu-id="8cf71-172">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="8cf71-173">Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)</span><span class="sxs-lookup"><span data-stu-id="8cf71-173">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="8cf71-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="8cf71-174">See Also</span></span>

* [<span data-ttu-id="8cf71-175">Настройка опрашивающего клиента с именами конфигураций</span><span class="sxs-lookup"><span data-stu-id="8cf71-175">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)
