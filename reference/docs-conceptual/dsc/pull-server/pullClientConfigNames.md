---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше
ms.openlocfilehash: d591e2a757130ccecaf4eaf9f363f607fca82b93
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953631"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a><span data-ttu-id="1463a-103">Настройка опрашивающего клиента с помощью имен конфигурации в PowerShell 5.0 и выше</span><span class="sxs-lookup"><span data-stu-id="1463a-103">Set up a Pull Client using Configuration Names in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="1463a-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="1463a-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1463a-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="1463a-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="1463a-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="1463a-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="1463a-107">Перед настройкой опрашивающего клиента необходимо настроить опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="1463a-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="1463a-108">Хотя этот порядок необязателен, он помогает устранять неполадки и гарантировать, что регистрация пройдет успешно.</span><span class="sxs-lookup"><span data-stu-id="1463a-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="1463a-109">Чтобы настроить опрашиваемый сервер, можно воспользоваться следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="1463a-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="1463a-110">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="1463a-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="1463a-111">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="1463a-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="1463a-112">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="1463a-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="1463a-113">В следующих разделах описана настройка опрашивающего клиента с общим ресурсом SMB или опрашиваемым сервером DSC HTTP.</span><span class="sxs-lookup"><span data-stu-id="1463a-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="1463a-114">При обновлении узла LCM он будет связываться с настроенным расположением для скачивания всех назначенных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="1463a-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="1463a-115">Если необходимые ресурсы отсутствуют на узле, он автоматически скачивает их из настроенного расположения.</span><span class="sxs-lookup"><span data-stu-id="1463a-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="1463a-116">Если на узле настроен [сервер отчетов](reportServer.md), затем он сообщит о состоянии операции.</span><span class="sxs-lookup"><span data-stu-id="1463a-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="1463a-117">Этот раздел относится к PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="1463a-117">This topic applies to PowerShell 5.0.</span></span>
> <span data-ttu-id="1463a-118">Сведения о настройке опрашивающего клиента в PowerShell 4.0 см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации в PowerShell 4.0](pullClientConfigID4.md)</span><span class="sxs-lookup"><span data-stu-id="1463a-118">For information on setting up a pull client in PowerShell 4.0, see [Set up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="1463a-119">Настройка LCM опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="1463a-119">Configure the pull client LCM</span></span>

<span data-ttu-id="1463a-120">После запуска любого из примеров ниже будет создана новая выходная папка **PullClientConfigNames**, в которую будет помещен MOF-файл метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="1463a-120">Executing any of the examples below creates a new output folder named **PullClientConfigName** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="1463a-121">В этом случае MOF-файл метаконфигурации будет называться `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="1463a-121">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="1463a-122">Чтобы применить конфигурацию, вызовите командлет **Set-DscLocalConfigurationManager**, в параметре **Path** которого задано расположение MOF-файла метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="1463a-122">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="1463a-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="1463a-123">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a><span data-ttu-id="1463a-124">Имя конфигурации</span><span class="sxs-lookup"><span data-stu-id="1463a-124">Configuration Name</span></span>

<span data-ttu-id="1463a-125">В примерах ниже в свойстве **ConfigurationName** LCM задается имя ранее скомпилированной конфигурации, созданной для этой цели.</span><span class="sxs-lookup"><span data-stu-id="1463a-125">The examples below sets the **ConfigurationName** property of the LCM to the name of a previously compiled Configuration, created for this purpose.</span></span> <span data-ttu-id="1463a-126">Имя **ConfigurationName** — это то, что LCM использует для поиска соответствующей конфигурации на опрашиваемом сервере.</span><span class="sxs-lookup"><span data-stu-id="1463a-126">The **ConfigurationName** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="1463a-127">MOF-файл конфигурации на опрашиваемом сервере должен называться `<ConfigurationName>.mof`, в данном случае "ClientConfig.mof".</span><span class="sxs-lookup"><span data-stu-id="1463a-127">The configuration MOF file on the pull server must be named `<ConfigurationName>.mof`, in this case, "ClientConfig.mof".</span></span> <span data-ttu-id="1463a-128">Дополнительные сведения см. в разделе [Публикация конфигураций на опрашиваемом сервере (версии 4 и 5)](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="1463a-128">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="1463a-129">Настройка опрашивающего клиента для скачивания конфигураций</span><span class="sxs-lookup"><span data-stu-id="1463a-129">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="1463a-130">Каждый клиент должен быть настроен в **опрашивающем** режиме с URL-адресом опрашиваемого сервера, где хранится конфигурация.</span><span class="sxs-lookup"><span data-stu-id="1463a-130">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="1463a-131">Для этого потребуется настроить локальный диспетчер конфигураций (LCM), указав обязательную информацию.</span><span class="sxs-lookup"><span data-stu-id="1463a-131">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="1463a-132">Чтобы настроить LCM, создайте специальный тип конфигурации, помеченный атрибутом **DSCLocalConfigurationManager**.</span><span class="sxs-lookup"><span data-stu-id="1463a-132">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="1463a-133">Дополнительные сведения о настройке LCM см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="1463a-133">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="1463a-134">Следующий сценарий настраивает LCM для опроса конфигураций с сервера CONTOSO-PullSrv.</span><span class="sxs-lookup"><span data-stu-id="1463a-134">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

- <span data-ttu-id="1463a-135">В сценарии блок **ConfigurationRepositoryWeb** задает опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="1463a-135">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="1463a-136">Свойство **ServerURL** указывает конечную точку для опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="1463a-136">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

- <span data-ttu-id="1463a-137">Свойство **RegistrationKey** является общим ключом между всеми узлами клиента для опрашивающего сервера и их опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="1463a-137">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span> <span data-ttu-id="1463a-138">Те же значения хранятся в файле на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="1463a-138">The same value is stored in a file on the pull server.</span></span>
  > [!NOTE]
  > <span data-ttu-id="1463a-139">Ключи регистрации работают только с опрашиваемыми **веб-серверами**.</span><span class="sxs-lookup"><span data-stu-id="1463a-139">Registration keys work only with **web** pull servers.</span></span> <span data-ttu-id="1463a-140">Вам по-прежнему следует использовать **ConfigurationID** с опрашиваемым сервером **SMB**.</span><span class="sxs-lookup"><span data-stu-id="1463a-140">You must still use **ConfigurationID** with an **SMB** pull server.</span></span>
  > <span data-ttu-id="1463a-141">Сведения о настройке опрашивающего сервера с использованием **ConfigurationID** см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации](pullClientConfigId.md)</span><span class="sxs-lookup"><span data-stu-id="1463a-141">For information about configuring a pull server by using **ConfigurationID**, see [Setting up a pull client using configuration ID](pullClientConfigId.md)</span></span>

- <span data-ttu-id="1463a-142">Свойство **ConfigurationNames** представляет собой массив, указывающий имена конфигураций, предназначенных для узла клиента.</span><span class="sxs-lookup"><span data-stu-id="1463a-142">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span>
  ><span data-ttu-id="1463a-143">**Примечание.** Если для параметра **ConfigurationNames** указано больше одного значения, в конфигурации необходимо также указать блоки **PartialConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1463a-143">**Note:** If you specify more than one value in the **ConfigurationNames**, you must also specify **PartialConfiguration** blocks in your configuration.</span></span>
  ><span data-ttu-id="1463a-144">Сведения о частичных конфигурациях см. в статье [Частичные конфигурации службы настройки требуемого состояния PowerShell](partialConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="1463a-144">For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

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

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="1463a-145">Настройка опрашивающего клиента для скачивания ресурсов</span><span class="sxs-lookup"><span data-stu-id="1463a-145">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="1463a-146">Если указать только блок **ConfigurationRepositoryWeb** или **ConfigurationRepositoryShare** в конфигурации LCM (как в предыдущем примере), опрашивающий клиент будет получать ресурсы оттуда же, где хранятся ваши MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="1463a-146">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from same location where your ".mof" files are stored.</span></span> <span data-ttu-id="1463a-147">Можно также указать другое место, откуда клиенты смогут скачивать ресурсы.</span><span class="sxs-lookup"><span data-stu-id="1463a-147">You can also specify different locations where clients can download resources.</span></span> <span data-ttu-id="1463a-148">Чтобы указать сервер ресурсов, используйте **ResourceRepositoryWeb** (для опрашивающего веб-сервера) или блок **ResourceRepositoryShare** (для опрашивающего SMB-сервера).</span><span class="sxs-lookup"><span data-stu-id="1463a-148">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>

<span data-ttu-id="1463a-149">В следующем примере показана метаконфигурация, которая настраивает клиент для скачивания конфигураций с опрашиваемого сервера, а ресурсов — с общего ресурса SMB.</span><span class="sxs-lookup"><span data-stu-id="1463a-149">The following example shows a metaconfiguration that sets up a client to download configurations from a Pull Server, and resources from an SMB share.</span></span>

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

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="1463a-150">Настройка опрашивающего клиента для отчета о состоянии</span><span class="sxs-lookup"><span data-stu-id="1463a-150">Set up a Pull Client to report status</span></span>

<span data-ttu-id="1463a-151">Можно использовать один и тот же опрашиваемый сервер для конфигурации, ресурсов и создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="1463a-151">You can use a single pull server for configurations, resources, and reporting.</span></span> <span data-ttu-id="1463a-152">Отчеты не настраиваются для клиентов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1463a-152">Reporting is not configured for clients by default.</span></span> <span data-ttu-id="1463a-153">Чтобы настроить клиент для отчета о состоянии, необходимо создать блок **ReportRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="1463a-153">To configure a client to report status, you have to create a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="1463a-154">В следующем примере показана метаконфигурация, которая настраивает клиент для опроса конфигураций и ресурсов и отправки данных отчетов на одном опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="1463a-154">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="1463a-155">Сервер отчетов не может быть общим ресурсом SMB.</span><span class="sxs-lookup"><span data-stu-id="1463a-155">A report server cannot be an SMB share.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1463a-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="1463a-156">See Also</span></span>

* [<span data-ttu-id="1463a-157">Настройка опрашивающего клиента с идентификатором конфигурации</span><span class="sxs-lookup"><span data-stu-id="1463a-157">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
* [<span data-ttu-id="1463a-158">Настройка опрашивающего веб-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="1463a-158">Setting up a DSC web pull server</span></span>](pullServer.md)
