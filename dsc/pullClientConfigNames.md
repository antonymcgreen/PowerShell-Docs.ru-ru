---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью имен конфигураций
ms.openlocfilehash: 7c8f204cc646e52ad5e953d6c7ad9e4e906d8a5b
ms.sourcegitcommit: ece1794c94be4880a2af5a2605ed4721593643b6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="setting-up-a-pull-client-using-configuration-names"></a><span data-ttu-id="d79bf-103">Настройка опрашивающего клиента с помощью имен конфигураций</span><span class="sxs-lookup"><span data-stu-id="d79bf-103">Setting up a pull client using configuration names</span></span>

> <span data-ttu-id="d79bf-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d79bf-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d79bf-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="d79bf-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="d79bf-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="d79bf-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="d79bf-107">Для каждого целевого узла нужно задать использование опрашивающего режима и URL-адреса, по которому можно подключиться к опрашивающему серверу для получения конфигураций.</span><span class="sxs-lookup"><span data-stu-id="d79bf-107">Each target node has to be told to use pull mode and given the URL where it can contact the pull server to get configurations.</span></span>
<span data-ttu-id="d79bf-108">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="d79bf-108">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span>
<span data-ttu-id="d79bf-109">Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="d79bf-109">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span>
<span data-ttu-id="d79bf-110">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="d79bf-110">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).</span></span>

> <span data-ttu-id="d79bf-111">**Примечание**. Этот раздел относится к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="d79bf-111">**Note**: This topic applies to PowerShell 5.0.</span></span>
<span data-ttu-id="d79bf-112">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="d79bf-112">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

<span data-ttu-id="d79bf-113">Следующий сценарий настраивает LCM для получения конфигураций с сервера CONTOSO-PullSrv:</span><span class="sxs-lookup"><span data-stu-id="d79bf-113">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv":</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }
    }
}
PullClientConfigNames
```

<span data-ttu-id="d79bf-114">В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="d79bf-114">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span>
<span data-ttu-id="d79bf-115">Свойство **ServerURL** указывает конечную точку для опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="d79bf-115">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

<span data-ttu-id="d79bf-116">Свойство **RegistrationKey** является общим ключом между всеми узлами клиента для опрашивающего сервера и их опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="d79bf-116">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span>
<span data-ttu-id="d79bf-117">Те же значения хранятся в файле на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="d79bf-117">The same value is stored in a file on the pull server.</span></span>

<span data-ttu-id="d79bf-118">Свойство **ConfigurationNames** представляет собой массив, указывающий имена конфигураций, предназначенных для узла клиента.</span><span class="sxs-lookup"><span data-stu-id="d79bf-118">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span>
<span data-ttu-id="d79bf-119">На опрашивающем сервере необходимо назвать MOF-файл конфигурации для этого узла клиента *ConfigurationNames*.mof, где *ConfigurationNames* соответствует значению свойства **ConfigurationNames**, заданному в этой метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="d79bf-119">On the pull server, the configuration MOF file for this client node must be named *ConfigurationNames*.mof, where *ConfigurationNames* matches the value of the **ConfigurationNames** property you set in this metaconfiguration.</span></span>

><span data-ttu-id="d79bf-120">**Примечание.** Если для параметра **ConfigurationNames** указано больше одного значения, в конфигурации необходимо также указать блоки **PartialConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d79bf-120">**Note:** If you specify more than one value in the **ConfigurationNames**, you must also specify **PartialConfiguration** blocks in your configuration.</span></span>
<span data-ttu-id="d79bf-121">Сведения о частичных конфигурациях см. в статье [Частичные конфигурации службы настройки требуемого состояния PowerShell](partialConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="d79bf-121">For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

<span data-ttu-id="d79bf-122">После запуска этого скрипта будет создана новая выходная папка **PullClientConfigNames**, в которую будет помещен MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="d79bf-122">After this script runs, it creates a new output folder named **PullClientConfigNames** and puts a metaconfiguration MOF file there.</span></span>
<span data-ttu-id="d79bf-123">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="d79bf-123">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="d79bf-124">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="d79bf-124">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span>

```powershell
Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigNames –Verbose.
```

> <span data-ttu-id="d79bf-125">**Примечание**. Ключи регистрации работают только с опрашивающими веб-серверами.</span><span class="sxs-lookup"><span data-stu-id="d79bf-125">**Note**: Registration keys work only with web pull servers.</span></span>
<span data-ttu-id="d79bf-126">Вам по-прежнему следует использовать **ConfigurationID** с опрашивающим SMB-сервером.</span><span class="sxs-lookup"><span data-stu-id="d79bf-126">You must still use **ConfigurationID** with an SMB pull server.</span></span>
<span data-ttu-id="d79bf-127">Сведения о настройке опрашивающего сервера с использованием **ConfigurationID** см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации](PullClientConfigNames.md)</span><span class="sxs-lookup"><span data-stu-id="d79bf-127">For information about configuring a pull server by using **ConfigurationID**, see [Setting up a pull client using configuration ID](PullClientConfigNames.md)</span></span>

## <a name="resource-and-report-servers"></a><span data-ttu-id="d79bf-128">Серверы ресурсов и отчетов</span><span class="sxs-lookup"><span data-stu-id="d79bf-128">Resource and report servers</span></span>

<span data-ttu-id="d79bf-129">Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы с указанного сервера, но не будет отправлять отчеты на этот сервер.</span><span class="sxs-lookup"><span data-stu-id="d79bf-129">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from the specified server, but it will not send reports to it.</span></span>
<span data-ttu-id="d79bf-130">Можно использовать один и тот же опрашивающий сервер для конфигураций, ресурсов и создания отчетов, но необходимо создать блок **ReportRepositoryWeb** для настройки отчетов.</span><span class="sxs-lookup"><span data-stu-id="d79bf-130">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>
<span data-ttu-id="d79bf-131">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="d79bf-131">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigNames
```

<span data-ttu-id="d79bf-132">При этом можно указать различные опрашивающие серверы для ресурсов и отчетов.</span><span class="sxs-lookup"><span data-stu-id="d79bf-132">You can also specify different pull servers for resources and reporting.</span></span>
<span data-ttu-id="d79bf-133">Чтобы указать сервер ресурсов, используйте **ResourceRepositoryWeb** (для опрашивающего веб-сервера) или блок **ResourceRepositoryShare** (для опрашивающего SMB-сервера).</span><span class="sxs-lookup"><span data-stu-id="d79bf-133">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>
<span data-ttu-id="d79bf-134">Чтобы указать сервер отчетов, используйте блок **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="d79bf-134">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span>
<span data-ttu-id="d79bf-135">Сервер отчетов не может быть SMB-сервером.</span><span class="sxs-lookup"><span data-stu-id="d79bf-135">A report server cannot be an SMB server.</span></span>
<span data-ttu-id="d79bf-136">Следующая метаконфигурация настраивает опрашивающий клиент для получения конфигураций из **CONTOSO-PullSrv** и ресурсов из **CONTOSO-ResourceSrv**, а также для отправки отчетов о состоянии на **CONTOSO-ReportSrv**:</span><span class="sxs-lookup"><span data-stu-id="d79bf-136">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-ResourceSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '30ef9bd8-9acf-4e01-8374-4dc35710fc90'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-ReportSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '6b392c6a-818c-4b24-bf38-47124f1e2f14'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a><span data-ttu-id="d79bf-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d79bf-137">See Also</span></span>

* [<span data-ttu-id="d79bf-138">Настройка опрашивающего клиента с идентификатором конфигурации</span><span class="sxs-lookup"><span data-stu-id="d79bf-138">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
* [<span data-ttu-id="d79bf-139">Настройка опрашивающего веб-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="d79bf-139">Setting up a DSC web pull server</span></span>](pullServer.md)