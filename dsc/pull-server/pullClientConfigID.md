---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройте опрашивающий клиент, используя идентификаторы конфигурации в PowerShell 5.0 и более поздних версий
ms.openlocfilehash: 8d8cf478f9127e1b7005d1b9e832e84b11612c9c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402784"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a><span data-ttu-id="91560-103">Настройте опрашивающий клиент, используя идентификаторы конфигурации в PowerShell 5.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="91560-103">Set up a Pull Client using Configuration IDs in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="91560-104">Область применения. Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="91560-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91560-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="91560-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="91560-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="91560-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="91560-107">Перед настройкой опрашивающего клиента, необходимо настроить опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="91560-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="91560-108">На то, что этот порядок не задан, он помогает устранять неполадки и помогает убедиться, что регистрация прошла успешно.</span><span class="sxs-lookup"><span data-stu-id="91560-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="91560-109">Чтобы настроить опрашивающий сервер, можно использовать со следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="91560-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="91560-110">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="91560-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="91560-111">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="91560-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="91560-112">Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии.</span><span class="sxs-lookup"><span data-stu-id="91560-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="91560-113">В следующих разделах описана настройка опрашивающего клиента с общий ресурс SMB или опрашивающего сервера DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="91560-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="91560-114">При обновлении узла LCM, он будет связываться в настроенное расположение для загрузки любого назначенных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="91560-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="91560-115">Если все необходимые ресурсы не существуют на узле, он автоматически скачивает их из настроенного расположения.</span><span class="sxs-lookup"><span data-stu-id="91560-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="91560-116">Если на узле настраивается с помощью [сервер отчетов](reportServer.md), затем он сообщит состояние операции.</span><span class="sxs-lookup"><span data-stu-id="91560-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> <span data-ttu-id="91560-117">**Примечание**. Этот раздел относится к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="91560-117">**Note**: This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="91560-118">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="91560-118">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="91560-119">Настройка опрашивающего клиента LCM</span><span class="sxs-lookup"><span data-stu-id="91560-119">Configure the pull client LCM</span></span>

<span data-ttu-id="91560-120">Выполнение любой из приведенных ниже примерах создается новая выходная папка с именем **PullClientConfigID** и MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="91560-120">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="91560-121">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="91560-121">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="91560-122">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="91560-122">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="91560-123">Например:</span><span class="sxs-lookup"><span data-stu-id="91560-123">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="91560-124">Идентификатор конфигурации</span><span class="sxs-lookup"><span data-stu-id="91560-124">Configuration ID</span></span>

<span data-ttu-id="91560-125">В примерах ниже наборы **ConfigurationID** в lcm на **Guid** , было создано для этой цели.</span><span class="sxs-lookup"><span data-stu-id="91560-125">The examples below sets the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="91560-126">Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="91560-126">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="91560-127">MOF-файл конфигурации на опрашивающем сервере должен иметь имя `ConfigurationID.mof`, где *ConfigurationID* является значением свойства **ConfigurationID** LCM целевого узла.</span><span class="sxs-lookup"><span data-stu-id="91560-127">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="91560-128">Дополнительные сведения см. в разделе [конфигураций публикации опрашивающий сервер (v4/v5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="91560-128">For more information see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="91560-129">Можно создать случайный **Guid** в примере ниже, или с помощью [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) командлета.</span><span class="sxs-lookup"><span data-stu-id="91560-129">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="91560-130">Дополнительные сведения об использовании **идентификаторы GUID** в вашей среде, см. в разделе [планирование идентификаторы GUID](/powershell/dsc/secureserver#guids).</span><span class="sxs-lookup"><span data-stu-id="91560-130">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/dsc/secureserver#guids).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="91560-131">Настройка клиента на включение внесенных изменений для загрузки конфигураций</span><span class="sxs-lookup"><span data-stu-id="91560-131">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="91560-132">Каждый клиент должен быть настроен в **по запросу** режима и URL-адрес сервера по запросу хранения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="91560-132">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="91560-133">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="91560-133">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="91560-134">Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="91560-134">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="91560-135">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="91560-135">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="91560-136">DSC опрашивающий HTTP-сервер</span><span class="sxs-lookup"><span data-stu-id="91560-136">HTTP DSC Pull Server</span></span>

<span data-ttu-id="91560-137">Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.</span><span class="sxs-lookup"><span data-stu-id="91560-137">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

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

<span data-ttu-id="91560-138">В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="91560-138">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="91560-139">**ServerUrl** указывает URL-адрес DSC Pull</span><span class="sxs-lookup"><span data-stu-id="91560-139">The **ServerUrl** specifies the url of the DSC Pull</span></span>

### <a name="smb-share"></a><span data-ttu-id="91560-140">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="91560-140">SMB Share</span></span>

<span data-ttu-id="91560-141">Следующий сценарий настраивает LCM для опроса конфигураций из общей папки SMB `\\SMBPullServer\Pull`.</span><span class="sxs-lookup"><span data-stu-id="91560-141">The following script configures the LCM to pull configurations from the SMB Share `\\SMBPullServer\Pull`.</span></span>

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

<span data-ttu-id="91560-142">В скрипте **ConfigurationRepositoryShare** блок задает опрашивающий сервер, который в данном случае является ресурс SMB.</span><span class="sxs-lookup"><span data-stu-id="91560-142">In the script, the **ConfigurationRepositoryShare** block defines the pull server, which in this case, is just an SMB share.</span></span>

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="91560-143">Настройка клиента на включение внесенных изменений для загрузки ресурсов</span><span class="sxs-lookup"><span data-stu-id="91560-143">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="91560-144">Если указать только **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** блока в конфигурации LCM (как в предыдущих примерах), опрашивающий клиент будет получать ресурсы из того же расположение, он извлекает его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="91560-144">If you specify only the **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous examples), the pull client will pull resources from the same location it retrieves its configurations.</span></span> <span data-ttu-id="91560-145">Можно также указать различные расположения для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="91560-145">You can also specify separate locations for resources.</span></span> <span data-ttu-id="91560-146">Чтобы указать расположение ресурсов как отдельный сервер, используйте **ResourceRepositoryWeb** блока.</span><span class="sxs-lookup"><span data-stu-id="91560-146">To specify a resource location as a separate server, use the **ResourceRepositoryWeb** block.</span></span> <span data-ttu-id="91560-147">Чтобы указать расположение ресурсов как ресурс SMB, используйте **ResourceRepositoryShare** блока.</span><span class="sxs-lookup"><span data-stu-id="91560-147">To specify a resource location as an SMB share, use the **ResourceRepositoryShare** block.</span></span>

> [!NOTE]
> <span data-ttu-id="91560-148">Вы можете объединить **ConfigurationRepositoryWeb** с **ResourceRepositoryShare** или **ConfigurationRepositoryShare** с **ResourceRepositoryWeb** .</span><span class="sxs-lookup"><span data-stu-id="91560-148">You can combine **ConfigurationRepositoryWeb** with **ResourceRepositoryShare** or **ConfigurationRepositoryShare** with **ResourceRepositoryWeb**.</span></span> <span data-ttu-id="91560-149">Не в качестве примера приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="91560-149">Examples of this are not shown below.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="91560-150">DSC опрашивающий HTTP-сервер</span><span class="sxs-lookup"><span data-stu-id="91560-150">HTTP DSC Pull Server</span></span>

<span data-ttu-id="91560-151">Следующая метаконфигурация настраивает на опрашивающем клиенте получение конфигураций из **CONTOSO-PullSrv** и его ресурсы из **CONTOSO-ResourceSrv**.</span><span class="sxs-lookup"><span data-stu-id="91560-151">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**.</span></span>

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

### <a name="smb-share"></a><span data-ttu-id="91560-152">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="91560-152">SMB Share</span></span>

<span data-ttu-id="91560-153">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций из общей папки SMB `\\SMBPullServer\Configurations`и ресурсы из общей папки SMB `\\SMBPullServer\Resources`.</span><span class="sxs-lookup"><span data-stu-id="91560-153">The following example shows a metaconfiguration that sets up a client to pull configurations from the SMB share `\\SMBPullServer\Configurations`, and resources from the SMB share `\\SMBPullServer\Resources`.</span></span>

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

#### <a name="automatically-download-resources-in-push-mode"></a><span data-ttu-id="91560-154">Автоматически загружать ресурсы в режиме Push</span><span class="sxs-lookup"><span data-stu-id="91560-154">Automatically download Resources in Push Mode</span></span>

<span data-ttu-id="91560-155">Начиная с PowerShell 5.0, клиенты по запросу можно скачать модули из общей папки SMB, даже в том случае, если они настроены для **Push** режим.</span><span class="sxs-lookup"><span data-stu-id="91560-155">Beginning in PowerShell 5.0, your pull clients can download modules from an SMB share, even when they are configured for **Push** mode.</span></span> <span data-ttu-id="91560-156">Это особенно полезно в сценариях, где вы хотите настроить сервер на включение внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="91560-156">This is especially useful in scenarios where you do not want to set up a Pull Server.</span></span> <span data-ttu-id="91560-157">**ResourceRepositoryShare** блок может использоваться без указания **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="91560-157">The **ResourceRepositoryShare** block can be used without specifying a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="91560-158">В следующем примере показана метаконфигурация, которая настраивает клиент для извлечения ресурсов из общей папки SMB `\\SMBPullServer\Resources`.</span><span class="sxs-lookup"><span data-stu-id="91560-158">The following example shows a metaconfiguration that sets up a client to pull resources from an SMB Share `\\SMBPullServer\Resources`.</span></span> <span data-ttu-id="91560-159">Когда этот узел находится **PUSHED** конфигурации, он автоматически скачивает все необходимые ресурсы, указанный общий ресурс.</span><span class="sxs-lookup"><span data-stu-id="91560-159">When the Node is **PUSHED** a configuration, it will automatically download any required resources, from the share specified.</span></span>

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

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="91560-160">Настройка клиента на включение внесенных изменений для отчета о состоянии</span><span class="sxs-lookup"><span data-stu-id="91560-160">Set up a Pull Client to report status</span></span>

<span data-ttu-id="91560-161">По умолчанию узлы не отправляют отчеты к настроенному серверу на включение внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="91560-161">By default, Nodes will not send reports to a configured Pull Server.</span></span> <span data-ttu-id="91560-162">Можно использовать один и тот же опрашивающий сервер для конфигураций, ресурсов и создания отчетов, но необходимо создать блок **ReportRepositoryWeb** для настройки отчетов.</span><span class="sxs-lookup"><span data-stu-id="91560-162">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="91560-163">DSC опрашивающий HTTP-сервер</span><span class="sxs-lookup"><span data-stu-id="91560-163">HTTP DSC Pull Server</span></span>

<span data-ttu-id="91560-164">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="91560-164">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

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

<span data-ttu-id="91560-165">Чтобы указать сервер отчетов, используйте блок **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="91560-165">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="91560-166">Сервер отчетов не может быть SMB-сервером.</span><span class="sxs-lookup"><span data-stu-id="91560-166">A report server cannot be an SMB server.</span></span>
<span data-ttu-id="91560-167">Следующая метаконфигурация настраивает опрашивающий клиент для получения конфигураций из **CONTOSO-PullSrv** и ресурсов из **CONTOSO-ResourceSrv**, а также для отправки отчетов о состоянии на **CONTOSO-ReportSrv**:</span><span class="sxs-lookup"><span data-stu-id="91560-167">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

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

### <a name="smb-share"></a><span data-ttu-id="91560-168">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="91560-168">SMB Share</span></span>

<span data-ttu-id="91560-169">Сервер отчетов не может быть общей папке SMB.</span><span class="sxs-lookup"><span data-stu-id="91560-169">A report server cannot be an SMB share.</span></span>

## <a name="next-steps"></a><span data-ttu-id="91560-170">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="91560-170">Next Steps</span></span>

<span data-ttu-id="91560-171">После настройки опрашивающий клиент, можно использовать со следующими руководствами для выполните следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="91560-171">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="91560-172">Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)</span><span class="sxs-lookup"><span data-stu-id="91560-172">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="91560-173">Упаковка и передача ресурсов на опрашиваемый сервер (версия 4)</span><span class="sxs-lookup"><span data-stu-id="91560-173">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="91560-174">См. также</span><span class="sxs-lookup"><span data-stu-id="91560-174">See Also</span></span>

* [<span data-ttu-id="91560-175">Настройка опрашивающего клиента с именами конфигураций</span><span class="sxs-lookup"><span data-stu-id="91560-175">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)
