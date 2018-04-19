---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью идентификатора конфигурации
ms.openlocfilehash: 95dfb4a182f9ecf592ae8c53e47fde4418ed6a8a
ms.sourcegitcommit: ece1794c94be4880a2af5a2605ed4721593643b6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="setting-up-a-pull-client-using-configuration-id"></a><span data-ttu-id="0ad9d-103">Настройка опрашивающего клиента с помощью идентификатора конфигурации</span><span class="sxs-lookup"><span data-stu-id="0ad9d-103">Setting up a pull client using configuration ID</span></span>

> <span data-ttu-id="0ad9d-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0ad9d-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ad9d-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="0ad9d-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="0ad9d-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="0ad9d-107">Для каждого целевого узла нужно задать использование опрашивающего режима и URL-адреса, по которому можно подключиться к опрашивающему серверу для получения конфигураций.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-107">Each target node has to be told to use pull mode and given the URL where it can contact the pull server to get configurations.</span></span> <span data-ttu-id="0ad9d-108">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-108">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="0ad9d-109">Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-109">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="0ad9d-110">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="0ad9d-110">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).</span></span>

> <span data-ttu-id="0ad9d-111">**Примечание**. Этот раздел относится к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-111">**Note**: This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="0ad9d-112">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="0ad9d-112">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

<span data-ttu-id="0ad9d-113">Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-113">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

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

<span data-ttu-id="0ad9d-114">В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-114">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="0ad9d-115">**ServerURL**</span><span class="sxs-lookup"><span data-stu-id="0ad9d-115">The **ServerURL**</span></span>

<span data-ttu-id="0ad9d-116">После запуска этого сценария будет создана новая выходная папка **PullClientConfigID**, в которую будет помещен MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-116">After this script runs, it creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="0ad9d-117">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-117">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="0ad9d-118">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-118">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="0ad9d-119">Пример: `Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigID –Verbose.`</span><span class="sxs-lookup"><span data-stu-id="0ad9d-119">For example: `Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigID –Verbose.`</span></span>

## <a name="configuration-id"></a><span data-ttu-id="0ad9d-120">Идентификатор конфигурации</span><span class="sxs-lookup"><span data-stu-id="0ad9d-120">Configuration ID</span></span>

<span data-ttu-id="0ad9d-121">Сценарий задает для свойства **ConfigurationID** LCM значение GUID, созданное специально для этой цели (вы можете создать GUID, используя командлет **New-Guid**).</span><span class="sxs-lookup"><span data-stu-id="0ad9d-121">The script sets the **ConfigurationID** property of LCM to a GUID that had been previously created for this purpose (you can create a GUID by using the **New-Guid** cmdlet).</span></span> <span data-ttu-id="0ad9d-122">Идентификатор **ConfigurationID** — это то, что LCM использует для поиска соответствующей конфигурации на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-122">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="0ad9d-123">MOF-файл конфигурации на опрашивающем сервере должен быть назван _ConfigurationID_.mof, где _ConfigurationID_ является значением свойства **ConfigurationID** LCM целевого узла.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-123">The configuration MOF file on the pull server must be named _ConfigurationID_.mof, where _ConfigurationID_ is the value of the **ConfigurationID** property of the target node's LCM.</span></span>

## <a name="smb-pull-server"></a><span data-ttu-id="0ad9d-124">Опрашивающий SMB-сервер</span><span class="sxs-lookup"><span data-stu-id="0ad9d-124">SMB pull server</span></span>

<span data-ttu-id="0ad9d-125">Чтобы настроить на клиенте опрос конфигураций с SMB-сервера, используйте блок **ConfigurationRepositoryShare**.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-125">To set up a client to pull configurations from an SMB server, use a **ConfigurationRepositoryShare** block.</span></span> <span data-ttu-id="0ad9d-126">В блоке **ConfigurationRepositoryShare** укажите путь к серверу, задав свойство **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-126">In a **ConfigurationRepositoryShare** block, you specify the path to the server by setting the **SourcePath** property.</span></span> <span data-ttu-id="0ad9d-127">Следующая метаконфигурация настраивает на целевом узле опрос с опрашивающего SMB-сервера **SMBPullServer**.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-127">The following metaconfiguration configures the target node to pull from an SMB pull server named **SMBPullServer**.</span></span>

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
            SourcePath = '\\SMBPullServer\PullSource'

        }
    }
}
PullClientConfigID
```

## <a name="resource-and-report-servers"></a><span data-ttu-id="0ad9d-128">Серверы ресурсов и отчетов</span><span class="sxs-lookup"><span data-stu-id="0ad9d-128">Resource and report servers</span></span>

<span data-ttu-id="0ad9d-129">Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы с указанного сервера, но не будет отправлять отчеты на этот сервер.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-129">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from the specified server, but it will not send reports to it.</span></span> <span data-ttu-id="0ad9d-130">Можно использовать один и тот же опрашивающий сервер для конфигураций, ресурсов и создания отчетов, но необходимо создать блок **ReportRepositoryWeb** для настройки отчетов.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-130">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

<span data-ttu-id="0ad9d-131">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-131">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

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

<span data-ttu-id="0ad9d-132">При этом можно указать различные опрашивающие серверы для ресурсов и отчетов.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-132">You can also specify different pull servers for resources and reporting.</span></span> <span data-ttu-id="0ad9d-133">Чтобы указать сервер ресурсов, используйте **ResourceRepositoryWeb** (для опрашивающего веб-сервера) или блок **ResourceRepositoryShare** (для опрашивающего SMB-сервера).</span><span class="sxs-lookup"><span data-stu-id="0ad9d-133">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>
<span data-ttu-id="0ad9d-134">Чтобы указать сервер отчетов, используйте блок **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-134">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="0ad9d-135">Сервер отчетов не может быть SMB-сервером.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-135">A report server cannot be an SMB server.</span></span>
<span data-ttu-id="0ad9d-136">Следующая метаконфигурация настраивает опрашивающий клиент для получения конфигураций из **CONTOSO-PullSrv** и ресурсов из **CONTOSO-ResourceSrv**, а также для отправки отчетов о состоянии на **CONTOSO-ReportSrv**:</span><span class="sxs-lookup"><span data-stu-id="0ad9d-136">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0ad9d-137">См. также</span><span class="sxs-lookup"><span data-stu-id="0ad9d-137">See Also</span></span>

* [<span data-ttu-id="0ad9d-138">Настройка опрашивающего клиента с именами конфигураций</span><span class="sxs-lookup"><span data-stu-id="0ad9d-138">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)