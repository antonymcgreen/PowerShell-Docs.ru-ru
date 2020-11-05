---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше
description: В этой статье описывается, как настроить опрашиваемый клиент с использованием имен конфигураций в PowerShell 5.0 и более поздних версий.
ms.openlocfilehash: db2b08605dd8bc7e48d9d5153861ce9b36118e21
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644917"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a><span data-ttu-id="ebdda-104">Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="ebdda-104">Set up a Pull Client using Configuration Names in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="ebdda-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ebdda-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebdda-106">Опрашивающий сервер (компонент Windows *служба DSC* ) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="ebdda-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="ebdda-107">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="ebdda-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="ebdda-108">Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="ebdda-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="ebdda-109">Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно.</span><span class="sxs-lookup"><span data-stu-id="ebdda-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="ebdda-110">Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="ebdda-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="ebdda-111">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="ebdda-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="ebdda-112">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="ebdda-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="ebdda-113">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="ebdda-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="ebdda-114">В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="ebdda-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="ebdda-115">При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ebdda-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="ebdda-116">Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения.</span><span class="sxs-lookup"><span data-stu-id="ebdda-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="ebdda-117">Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.</span><span class="sxs-lookup"><span data-stu-id="ebdda-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="ebdda-118">Этот раздел относится к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="ebdda-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="ebdda-119">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="ebdda-119">For information on setting up a pull client in PowerShell 4.0, see [Set up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="ebdda-120">Настройка LCM опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="ebdda-120">Configure the pull client LCM</span></span>

<span data-ttu-id="ebdda-121">После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigNames** , в которую будет помещен MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="ebdda-121">Executing any of the examples below creates a new output folder named **PullClientConfigName** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="ebdda-122">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="ebdda-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="ebdda-123">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager** , в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="ebdda-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="ebdda-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="ebdda-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a><span data-ttu-id="ebdda-125">Имя конфигурации</span><span class="sxs-lookup"><span data-stu-id="ebdda-125">Configuration Name</span></span>

<span data-ttu-id="ebdda-126">В примерах ниже в свойстве **ConfigurationName** LCM задается имя ранее скомпилированной конфигурации, созданной для этой цели.</span><span class="sxs-lookup"><span data-stu-id="ebdda-126">The examples below sets the **ConfigurationName** property of the LCM to the name of a previously compiled Configuration, created for this purpose.</span></span> <span data-ttu-id="ebdda-127">Имя **ConfigurationName** — это то, что LCM использует для поиска соответствующей конфигурации на опрашиваемом сервере.</span><span class="sxs-lookup"><span data-stu-id="ebdda-127">The **ConfigurationName** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="ebdda-128">MOF-файл конфигурации на опрашиваемом сервере должен называться `<ConfigurationName>.mof`, в данном случае "ClientConfig.mof".</span><span class="sxs-lookup"><span data-stu-id="ebdda-128">The configuration MOF file on the pull server must be named `<ConfigurationName>.mof`, in this case, "ClientConfig.mof".</span></span> <span data-ttu-id="ebdda-129">Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="ebdda-129">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="ebdda-130">Настройка опрашивающего клиента для скачивания конфигураций</span><span class="sxs-lookup"><span data-stu-id="ebdda-130">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="ebdda-131">Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация.</span><span class="sxs-lookup"><span data-stu-id="ebdda-131">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="ebdda-132">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="ebdda-132">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="ebdda-133">Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="ebdda-133">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="ebdda-134">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="ebdda-134">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="ebdda-135">Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.</span><span class="sxs-lookup"><span data-stu-id="ebdda-135">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

- <span data-ttu-id="ebdda-136">В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="ebdda-136">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="ebdda-137">Свойство **ServerURL** указывает конечную точку для опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="ebdda-137">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

- <span data-ttu-id="ebdda-138">Свойство **RegistrationKey** является общим ключом между всеми узлами клиента для опрашивающего сервера и этим опрашивающим сервером.</span><span class="sxs-lookup"><span data-stu-id="ebdda-138">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span> <span data-ttu-id="ebdda-139">Те же значения хранятся в файле на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="ebdda-139">The same value is stored in a file on the pull server.</span></span><span data-ttu-id="ebdda-140"> > [!NOTE] > Ключи регистрации работают только с опрашиваемыми **веб-серверами**.</span><span class="sxs-lookup"><span data-stu-id="ebdda-140"> > [!NOTE] > Registration keys work only with **web** pull servers.</span></span> <span data-ttu-id="ebdda-141">Вам по-прежнему следует использовать **ConfigurationID** с опрашиваемым сервером **SMB**.</span><span class="sxs-lookup"><span data-stu-id="ebdda-141">You must still use **ConfigurationID** with an **SMB** pull server.</span></span> <span data-ttu-id="ebdda-142">> Сведения о настройке опрашиваемого сервера с использованием **ConfigurationID** см. в статье [Настройка опрашиваемого клиента с помощью идентификатора конфигурации](pullClientConfigId.md).</span><span class="sxs-lookup"><span data-stu-id="ebdda-142">> For information about configuring a pull server by using **ConfigurationID** , see [Setting up a pull client using configuration ID](pullClientConfigId.md)</span></span>

- <span data-ttu-id="ebdda-143">Свойство **ConfigurationNames** представляет собой массив, указывающий имена конфигураций, предназначенных для узла клиента.</span><span class="sxs-lookup"><span data-stu-id="ebdda-143">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span><span data-ttu-id="ebdda-144"> >**Примечание**. Если для параметра **ConfigurationNames** указано больше одного значения, в конфигурации необходимо также указать блоки **PartialConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ebdda-144"> >**Note:** If you specify more than one value in the **ConfigurationNames** , you must also specify **PartialConfiguration** blocks in your configuration.</span></span> <span data-ttu-id="ebdda-145">> Сведения о частичных конфигурациях см. в статье [Частичные конфигурации Desired State Configuration в PowerShell](partialConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="ebdda-145">>For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

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

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="ebdda-146">Настройка опрашивающего клиента для скачивания ресурсов</span><span class="sxs-lookup"><span data-stu-id="ebdda-146">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="ebdda-147">Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы оттуда же, где хранятся ваши MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="ebdda-147">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from same location where your ".mof" files are stored.</span></span> <span data-ttu-id="ebdda-148">Можно также указать другое место, откуда клиенты смогут скачивать ресурсы.</span><span class="sxs-lookup"><span data-stu-id="ebdda-148">You can also specify different locations where clients can download resources.</span></span> <span data-ttu-id="ebdda-149">Чтобы указать сервер ресурсов, используйте **ResourceRepositoryWeb** (для опрашивающего веб-сервера) или блок **ResourceRepositoryShare** (для опрашивающего SMB-сервера).</span><span class="sxs-lookup"><span data-stu-id="ebdda-149">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>

<span data-ttu-id="ebdda-150">В следующем примере показана метаконфигурация, которая настраивает клиент для скачивания конфигураций с опрашиваемого сервера, а ресурсов — с общего ресурса SMB.</span><span class="sxs-lookup"><span data-stu-id="ebdda-150">The following example shows a metaconfiguration that sets up a client to download configurations from a Pull Server, and resources from an SMB share.</span></span>

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

        ResourceRepositoryShare SMBResources
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="ebdda-151">Настройка опрашивающего клиента для отчета о состоянии</span><span class="sxs-lookup"><span data-stu-id="ebdda-151">Set up a Pull Client to report status</span></span>

<span data-ttu-id="ebdda-152">Можно использовать один и тот же опрашиваемый сервер для конфигурации, ресурсов и создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="ebdda-152">You can use a single pull server for configurations, resources, and reporting.</span></span> <span data-ttu-id="ebdda-153">Отчеты не настраиваются для клиентов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ebdda-153">Reporting is not configured for clients by default.</span></span> <span data-ttu-id="ebdda-154">Чтобы настроить клиент для отчета о состоянии, необходимо создать блок **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="ebdda-154">To configure a client to report status, you have to create a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="ebdda-155">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="ebdda-155">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="ebdda-156">Сервер отчетов не может быть общим ресурсом SMB.</span><span class="sxs-lookup"><span data-stu-id="ebdda-156">A report server cannot be an SMB share.</span></span>

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
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a><span data-ttu-id="ebdda-157">См. также</span><span class="sxs-lookup"><span data-stu-id="ebdda-157">See Also</span></span>

- [<span data-ttu-id="ebdda-158">Настройка опрашивающего клиента с идентификатором конфигурации</span><span class="sxs-lookup"><span data-stu-id="ebdda-158">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
- [<span data-ttu-id="ebdda-159">Настройка опрашивающего веб-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="ebdda-159">Setting up a DSC web pull server</span></span>](pullServer.md)
