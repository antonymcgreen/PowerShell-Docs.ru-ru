---
ms.date: 04/11/2018
ms.topic: conceptual
keywords: dsc,powershell,конфигурация,установка
title: Опрашивающая служба DSC
ms.openlocfilehash: 61b4c0e9cfe1d1d7539cd32da35d2fe50da4b0e3
ms.sourcegitcommit: ece1794c94be4880a2af5a2605ed4721593643b6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="desired-state-configuration-pull-service"></a><span data-ttu-id="af125-103">Опрашивающая служба Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="af125-103">Desired State Configuration Pull Service</span></span>

> <span data-ttu-id="af125-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="af125-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af125-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="af125-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="af125-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="af125-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="af125-107">Управление локальным диспетчером конфигураций можно централизировать с помощью опрашивающей службы.</span><span class="sxs-lookup"><span data-stu-id="af125-107">Local Configuration Manager can be centrally managed by a Pull Service solution.</span></span>
<span data-ttu-id="af125-108">При использовании такого подхода управляемый узел регистрируется в службе, и ему в параметрах локального диспетчера конфигураций назначается конфигурация.</span><span class="sxs-lookup"><span data-stu-id="af125-108">When using this approach, the node that is being managed is registered with a service and assigned a configuration in LCM settings.</span></span>
<span data-ttu-id="af125-109">Конфигурация и все ресурсы DSC, которые необходимы в качестве зависимостей конфигурации, загружаются на компьютер и используются локальным диспетчером конфигураций для управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="af125-109">The configuration and all DSC resources needed as dependencies for the configuration are downloaded to the machine and used by LCM to manage the configuration.</span></span>
<span data-ttu-id="af125-110">Сведения о состоянии управляемого компьютера отправляются в службу для отчетности.</span><span class="sxs-lookup"><span data-stu-id="af125-110">Information about the state of the machine being managed is uploaded to the service for reporting.</span></span>
<span data-ttu-id="af125-111">Эта концепция называется "опрашивающей службой".</span><span class="sxs-lookup"><span data-stu-id="af125-111">This concept is referred to as "pull service."</span></span>

<span data-ttu-id="af125-112">Текущие варианты опрашиваемой службы:</span><span class="sxs-lookup"><span data-stu-id="af125-112">The current options for pull service include:</span></span>

- <span data-ttu-id="af125-113">служба Desired State Configuration в службе автоматизации Azure;</span><span class="sxs-lookup"><span data-stu-id="af125-113">Azure Automation Desired State Configuration service</span></span>
- <span data-ttu-id="af125-114">Опрашиваемая служба в Windows Server</span><span class="sxs-lookup"><span data-stu-id="af125-114">A pull service running on Windows Server</span></span>
- <span data-ttu-id="af125-115">Решения с открытым исходным кодом, поддерживаемые сообществом</span><span class="sxs-lookup"><span data-stu-id="af125-115">Community maintained open-source solutions</span></span>
- <span data-ttu-id="af125-116">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="af125-116">An SMB share</span></span>

<span data-ttu-id="af125-117">**Рекомендуемое решение** и вариант с наибольшим числом доступных функций — [DSC в службе автоматизации Azure](/azure/automation/automation-dsc-getting-started).</span><span class="sxs-lookup"><span data-stu-id="af125-117">**The recommended solution**, and the option with the most features available, is [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span>

<span data-ttu-id="af125-118">Служба Azure может управлять узлами в локальных частных центрах обработки данных или в общедоступных облаках, таких как Azure и AWS.</span><span class="sxs-lookup"><span data-stu-id="af125-118">The Azure service can manage nodes on-premises in private datacenters, or in public clouds such as Azure and AWS.</span></span>
<span data-ttu-id="af125-119">Для частных сред, где серверы не могут напрямую подключаться к Интернету, рекомендуем ограничить исходящий трафик только опубликованным диапазоном IP-адресов Azure (см. сведения о [диапазонах IP-адресов для центров обработки данных Azure](https://www.microsoft.com/en-us/download/details.aspx?id=41653)).</span><span class="sxs-lookup"><span data-stu-id="af125-119">For private environments where servers cannot directly connect to the Internet, consider limiting outbound traffic to only the published Azure IP range (see [Azure Datacenter IP Ranges](https://www.microsoft.com/en-us/download/details.aspx?id=41653)).</span></span>

<span data-ttu-id="af125-120">Функции веб-службы, которые сейчас недоступны в опрашиваемой службе в Windows Server:</span><span class="sxs-lookup"><span data-stu-id="af125-120">Features of the online service that are not currently available in the pull service on Windows Server include:</span></span>
- <span data-ttu-id="af125-121">Шифрование всех данных при передаче и хранении.</span><span class="sxs-lookup"><span data-stu-id="af125-121">All data is encrypted in transit and at rest</span></span>
- <span data-ttu-id="af125-122">Автоматическое создание и обслуживание клиентских сертификатов.</span><span class="sxs-lookup"><span data-stu-id="af125-122">Client certificates are created and managed automatically</span></span>
- <span data-ttu-id="af125-123">Хранение секретов с централизованным управлением [паролями и учетными данными](/azure/automation/automation-credentials) или [переменными](/azure/automation/automation-variables), такими как имена серверов или строки подключения.</span><span class="sxs-lookup"><span data-stu-id="af125-123">Secrets store for centrally managing [passwords/credentials](/azure/automation/automation-credentials), or [variables](/azure/automation/automation-variables) such as server names or connection strings</span></span>
- <span data-ttu-id="af125-124">Централизованное управление [конфигурацией LCM](metaConfig.md#basic-settings) в узле.</span><span class="sxs-lookup"><span data-stu-id="af125-124">Centrally manage node [LCM configuration](metaConfig.md#basic-settings)</span></span>
- <span data-ttu-id="af125-125">Централизованное назначение конфигураций клиентским узлам.</span><span class="sxs-lookup"><span data-stu-id="af125-125">Centrally assign configurations to client nodes</span></span>
- <span data-ttu-id="af125-126">Выпуск изменений конфигурации для небольших групп пользователей, позволяющий протестировать решение перед реализацией в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="af125-126">Release configuration changes to "canary groups" for testing before reaching production</span></span>
- <span data-ttu-id="af125-127">Графические отчеты:</span><span class="sxs-lookup"><span data-stu-id="af125-127">Graphical reporting</span></span>
  - <span data-ttu-id="af125-128">сведения о состоянии на уровне ресурсов DSC;</span><span class="sxs-lookup"><span data-stu-id="af125-128">Status detail at the DSC resource level of granularity</span></span>
  - <span data-ttu-id="af125-129">подробные сообщения об ошибках с клиентских компьютеров для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="af125-129">Verbose error messages from client machines for troubleshooting</span></span>
- <span data-ttu-id="af125-130">[Интеграция с Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) для отправки предупреждений, автоматизации задач, а также выполнения приложений Android или iOS для создания отчетов и оповещений.</span><span class="sxs-lookup"><span data-stu-id="af125-130">[Integration with Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) for alerting, automated tasks, Android/iOS app for reporting and alerting</span></span>

## <a name="dsc-pull-service-in-windows-server"></a><span data-ttu-id="af125-131">Опрашивающая служба DSC в Windows Server</span><span class="sxs-lookup"><span data-stu-id="af125-131">DSC pull service in Windows Server</span></span>

<span data-ttu-id="af125-132">Опрашиваемую службу можно настроить для работы в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="af125-132">It is possible to configuring a pull service to run on Windows Server.</span></span>
<span data-ttu-id="af125-133">Учтите, что опрашиваемая служба в составе Windows Server включает только возможности хранения конфигураций и модулей для скачивания и записи данных отчетов в базу данных.</span><span class="sxs-lookup"><span data-stu-id="af125-133">Be advised that the pull service solution included in Windows Server includes only capabilities of storing configurations/modules for download and capturing report data in to database.</span></span>
<span data-ttu-id="af125-134">Она не включает многих функций, предоставляемых службой в Azure, и поэтому не слишком хорошо подходит для оценки потенциального использования службы.</span><span class="sxs-lookup"><span data-stu-id="af125-134">It does not include many of the capabilities offered by the service in Azure and so is not a good tool for evaluating how the service would be used.</span></span>

<span data-ttu-id="af125-135">Опрашивающая служба в Windows Server — это веб-служба в составе IIS, которая использует интерфейс OData для создания файлов конфигурации DSC, доступных целевым узлам по запросу.</span><span class="sxs-lookup"><span data-stu-id="af125-135">The pull service offered in Windows Server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="af125-136">Требования к использованию опрашиваемого сервера:</span><span class="sxs-lookup"><span data-stu-id="af125-136">Requirements for using a pull server:</span></span>

- <span data-ttu-id="af125-137">Сервер под управлением:</span><span class="sxs-lookup"><span data-stu-id="af125-137">A server running:</span></span>
  - <span data-ttu-id="af125-138">WMF/PowerShell 5.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="af125-138">WMF/PowerShell 5.0 or greater</span></span>
  - <span data-ttu-id="af125-139">Роль сервера служб IIS</span><span class="sxs-lookup"><span data-stu-id="af125-139">IIS server role</span></span>
  - <span data-ttu-id="af125-140">Служба DSC</span><span class="sxs-lookup"><span data-stu-id="af125-140">DSC Service</span></span>
- <span data-ttu-id="af125-141">Рекомендуется использовать средства создания сертификата для защиты учетных данных, передаваемых в локальный диспетчер конфигураций (LCM) на целевых узлах</span><span class="sxs-lookup"><span data-stu-id="af125-141">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="af125-142">Для настройки размещения опрашивающей службы в Windows Server лучше всего воспользоваться конфигурацией DSC.</span><span class="sxs-lookup"><span data-stu-id="af125-142">The best way to configure Windows Server to host pull service is to use a DSC configuration.</span></span>
<span data-ttu-id="af125-143">Пример сценария приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="af125-143">An example script is provided below.</span></span>

### <a name="supported-database-systems"></a><span data-ttu-id="af125-144">Поддерживаемые системы баз данных</span><span class="sxs-lookup"><span data-stu-id="af125-144">Supported database systems</span></span>

|<span data-ttu-id="af125-145">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="af125-145">WMF 4.0</span></span>   |<span data-ttu-id="af125-146">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="af125-146">WMF 5.0</span></span>  |<span data-ttu-id="af125-147">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="af125-147">WMF 5.1</span></span> |<span data-ttu-id="af125-148">WMF 5.1 (Windows Server Insider Preview версии 17090)</span><span class="sxs-lookup"><span data-stu-id="af125-148">WMF 5.1 (Windows Server Insider Preview 17090)</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="af125-149">MDB</span><span class="sxs-lookup"><span data-stu-id="af125-149">MDB</span></span>     |<span data-ttu-id="af125-150">ESENT (по умолчанию), MDB</span><span class="sxs-lookup"><span data-stu-id="af125-150">ESENT (Default), MDB</span></span> |<span data-ttu-id="af125-151">ESENT (по умолчанию), MDB</span><span class="sxs-lookup"><span data-stu-id="af125-151">ESENT (Default), MDB</span></span>|<span data-ttu-id="af125-152">ESENT (по умолчанию), SQL Server, MDB</span><span class="sxs-lookup"><span data-stu-id="af125-152">ESENT (Default), SQL Server, MDB</span></span>

<span data-ttu-id="af125-153">Начиная с выпуска 17090 [Windows Server Insider Preview](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewserver), в опрашивающей службе (компонент Windows *служба DSC*) поддерживается SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af125-153">Starting in release 17090 of [Windows Server Insider Preview](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewserver), SQL Server is a supported option for the Pull Service (Windows Feature *DSC-Service*).</span></span>  <span data-ttu-id="af125-154">Это новый вариант масштабирования крупных сред DSC, которые не были перенесены в [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span><span class="sxs-lookup"><span data-stu-id="af125-154">This provides a new option for scaling large DSC environments that have not migrated to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span>

> <span data-ttu-id="af125-155">**Примечание**. Поддержка SQL Server не будет добавлена в предыдущие версии WMF 5.1 (или более ранней версии) и будет доступна только в Windows Server версии 17090 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="af125-155">**Note**: SQL Server support will not be added to previous versions of WMF 5.1 (or earlier) and will only be available on Windows Server versions greater than or equal to 17090.</span></span>

<span data-ttu-id="af125-156">Чтобы настроить на опрашивающем сервере использование SQL Server, установите значение `$true` для параметра **SqlProvider** и допустимую строку подключения SQL Server для параметра **SqlConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="af125-156">To configure the pull server to use SQL Server, set **SqlProvider** to `$true` and **SqlConnectionString** to a valid SQL Server Connection String.</span></span>  <span data-ttu-id="af125-157">Дополнительные сведения см. в разделе [Строки подключения SqlClient](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span><span class="sxs-lookup"><span data-stu-id="af125-157">For more information, see [SqlClient Connection Strings](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span></span>
<span data-ttu-id="af125-158">Чтобы ознакомиться с настройкой SQL Server с помощью **xDscWebService**, прочтите статью [Использование ресурса xDscWebService](#using-the-xdscwebservice-resource) и просмотрите файл [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 в GitHub](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/master/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span><span class="sxs-lookup"><span data-stu-id="af125-158">For an example of SQL Server configuration with **xDscWebService**, first read [Using the xDscWebService resource](#using-the-xdscwebservice-resource) and then review [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 on GitHub](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/master/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span></span>

### <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="af125-159">Использование ресурса xDSCWebService</span><span class="sxs-lookup"><span data-stu-id="af125-159">Using the xDscWebService resource</span></span>

<span data-ttu-id="af125-160">Самый простой способ настроить опрашиваемый веб-сервер — использовать ресурс **xDscWebService**, включенный в модуль **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="af125-160">The easiest way to set up a web pull server is to use the **xDscWebService** resource, included in the **xPSDesiredStateConfiguration** module.</span></span>
<span data-ttu-id="af125-161">В следующих действиях показано, как использовать ресурс в конфигурации, которая настраивает веб-службу.</span><span class="sxs-lookup"><span data-stu-id="af125-161">The following steps explain how to use the resource in a configuration that sets up the web service.</span></span>

1. <span data-ttu-id="af125-162">Вызовите командлет [Install-Module](/powershell/module/PowershellGet/Install-Module), чтобы установить модуль **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="af125-162">Call the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="af125-163">**Примечание**. **Install-Module** включен в модуль **PowerShellGet**, содержащийся в PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="af125-163">**Note**: **Install-Module** is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span> <span data-ttu-id="af125-164">Вы можете скачать модуль **PowerShellGet**для PowerShell 3.0 и 4.0 в разделе [Предварительная версия модулей PackageManagement PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span><span class="sxs-lookup"><span data-stu-id="af125-164">You can download the **PowerShellGet** module for PowerShell 3.0 and 4.0 at [PackageManagement PowerShell Modules Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span></span>
1. <span data-ttu-id="af125-165">Получите SSL-сертификат для опрашивающего сервера DSC из доверенного центра сертификации (общедоступного или входящего в состав вашей организации).</span><span class="sxs-lookup"><span data-stu-id="af125-165">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="af125-166">Полученный из центра сертификат обычно имеет формат PFX.</span><span class="sxs-lookup"><span data-stu-id="af125-166">The certificate received from the authority is usually in the PFX format.</span></span> <span data-ttu-id="af125-167">Установите сертификат на узле, который должен стать опрашивающим сервером DSC, в расположении по умолчанию (CERT:\LocalMachine\My).</span><span class="sxs-lookup"><span data-stu-id="af125-167">Install the certificate on the node that will become the DSC Pull server in the default location, which should be CERT:\LocalMachine\My.</span></span> <span data-ttu-id="af125-168">Запишите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="af125-168">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="af125-169">Выберите идентификатор GUID для использования в качестве ключа регистрации.</span><span class="sxs-lookup"><span data-stu-id="af125-169">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="af125-170">Для его создания с помощью PowerShell введите следующие команды в командной строке PS и нажмите клавишу ВВОД: "``` [guid]::newGuid()```" или "```New-Guid```".</span><span class="sxs-lookup"><span data-stu-id="af125-170">To generate one using PowerShell enter the following at the PS prompt and press enter: '``` [guid]::newGuid()```' or '```New-Guid```'.</span></span> <span data-ttu-id="af125-171">Этот ключ будет использоваться клиентскими узлами в качестве общего ключа для проверки подлинности во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="af125-171">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="af125-172">Дополнительные сведения см. в разделе "Ключ регистрации" ниже.</span><span class="sxs-lookup"><span data-stu-id="af125-172">For more information, see the Registration Key section below.</span></span>
1. <span data-ttu-id="af125-173">В PowerShell ISE запустите (нажав клавишу F5) следующий сценарий конфигурации (находящийся в папке "Примеры" модуля **xPSDesiredStateConfiguration** в качестве  Sample_xDscWebServiceRegistration.ps1).</span><span class="sxs-lookup"><span data-stu-id="af125-173">In the PowerShell ISE, start (F5) the following configuration script (included in the Examples folder of the  **xPSDesiredStateConfiguration** module as Sample_xDscWebServiceRegistration.ps1).</span></span> <span data-ttu-id="af125-174">Этот сценарий настраивает опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="af125-174">This script sets up the pull server.</span></span>

```powershell
configuration Sample_xDscWebServiceRegistration
{
    param
    (
        [string[]]$NodeName = 'localhost',

        [ValidateNotNullOrEmpty()]
        [string] $certificateThumbPrint,

        [Parameter(HelpMessage='This should be a string with enough entropy (randomness) to protect the registration of clients to the pull server.  We will use new GUID by default.')]
        [ValidateNotNullOrEmpty()]
        [string] $RegistrationKey   # A guid that clients use to initiate conversation with pull server
    )

    Import-DSCResource -ModuleName xPSDesiredStateConfiguration

    Node $NodeName
    {
        WindowsFeature DSCServiceFeature
        {
            Ensure = "Present"
            Name   = "DSC-Service"
        }

        xDscWebService PSDSCPullServer
        {
            Ensure                  = "Present"
            EndpointName            = "PSDSCPullServer"
            Port                    = 8080
            PhysicalPath            = "$env:SystemDrive\inetpub\PSDSCPullServer"
            CertificateThumbPrint   = $certificateThumbPrint
            ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
            ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
            State                   = "Started"
            DependsOn               = "[WindowsFeature]DSCServiceFeature"
            RegistrationKeyPath     = "$env:PROGRAMFILES\WindowsPowerShell\DscService"
            AcceptSelfSignedCertificates = $true
            Enable32BitAppOnWin64   = $false
        }

        File RegistrationKeyFile
        {
            Ensure          = 'Present'
            Type            = 'File'
            DestinationPath = "$env:ProgramFiles\WindowsPowerShell\DscService\RegistrationKeys.txt"
            Contents        = $RegistrationKey
        }
    }
}
```

1. <span data-ttu-id="af125-175">Запустите конфигурацию, передав отпечаток SSL-сертификата в виде параметра **certificateThumbPrint** и ключ регистрации GUID в виде параметра **RegistrationKey**:</span><span class="sxs-lookup"><span data-stu-id="af125-175">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

```powershell
# To find the Thumbprint for an installed SSL certificate for use with the pull server list all certificates in your local store
# and then copy the thumbprint for the appropriate certificate by reviewing the certificate subjects
dir Cert:\LocalMachine\my

# Then include this thumbprint when running the configuration
Sample_xDSCPullServer -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

# Run the compiled configuration to make the target node a DSC Pull Server
Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose
```

#### <a name="registration-key"></a><span data-ttu-id="af125-176">Ключ регистрации</span><span class="sxs-lookup"><span data-stu-id="af125-176">Registration Key</span></span>

<span data-ttu-id="af125-177">Чтобы разрешить клиентским узлам регистрироваться на сервере для использования имен конфигурации вместо идентификаторов конфигурации, созданный конфигурацией ключ сохраняется в файле `RegistrationKeys.txt` в `C:\Program Files\WindowsPowerShell\DscService`.</span><span class="sxs-lookup"><span data-stu-id="af125-177">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key that was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="af125-178">Ключ регистрации работает как общий секрет, используемый во время первоначальной регистрации клиента с опрашивающим сервером.</span><span class="sxs-lookup"><span data-stu-id="af125-178">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="af125-179">Клиент создает самозаверяющий сертификат, который используется для уникальной проверки подлинности на опрашивающем сервере после успешного завершения регистрации.</span><span class="sxs-lookup"><span data-stu-id="af125-179">The client will generate a self-signed certificate that is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="af125-180">Отпечаток этого сертификата сохраняется локально и связывается с URL-адресом опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="af125-180">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>
> <span data-ttu-id="af125-181">**Примечание**. Ключи регистрации не поддерживаются в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="af125-181">**Note**: Registration keys are not supported in PowerShell 4.0.</span></span>

<span data-ttu-id="af125-182">Для настройки проверки подлинности узла на опрашивающем сервере необходимо поместить ключ регистрации в метаконфигурацию всех целевых узлов, которые будут регистрироваться на этом опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="af125-182">In order to configure a node to authenticate with the pull server, the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="af125-183">Обратите внимание, что **RegistrationKey** в метаконфигурации ниже удаляется после успешной регистрации целевого компьютера и значение "140a952b-b9d6-406b-b416-e0f759c9c0e4" должно соответствовать значению в файле RegistrationKeys.txt на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="af125-183">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value '140a952b-b9d6-406b-b416-e0f759c9c0e4' must match the value stored in the RegistrationKeys.txt file on the pull server.</span></span> <span data-ttu-id="af125-184">Значение ключа регистрации должно оставаться конфиденциальным, так как с ним любой целевой компьютер сможет зарегистрироваться на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="af125-184">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration Sample_MetaConfigurationToRegisterWithLessSecurePullServer
{
    param
    (
        [ValidateNotNullOrEmpty()]
        [string] $NodeName = 'localhost',

        [ValidateNotNullOrEmpty()]
        [string] $RegistrationKey, #same as the one used to setup pull server in previous configuration

        [ValidateNotNullOrEmpty()]
        [string] $ServerName = 'localhost' #node name of the pull server, same as $NodeName used in previous configuration
    )

    Node $NodeName
    {
        Settings
        {
            RefreshMode        = 'Pull'
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = "https://$ServerName`:8080/PSDSCPullServer.svc" # notice it is https
            RegistrationKey    = $RegistrationKey
            ConfigurationNames = @('ClientConfig')
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL       = "https://$ServerName`:8080/PSDSCPullServer.svc" # notice it is https
            RegistrationKey = $RegistrationKey
        }
    }
}

Sample_MetaConfigurationToRegisterWithLessSecurePullServer -RegistrationKey $RegistrationKey -OutputPath c:\Configs\TargetNodes
```

> <span data-ttu-id="af125-185">**Примечание**. Раздел **ReportServerWeb** позволяет отправлять данные отчетов на опрашивающий сервер.</span><span class="sxs-lookup"><span data-stu-id="af125-185">**Note**: The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span>

<span data-ttu-id="af125-186">Отсутствие свойства **ConfigurationID** в файле метаконфигурации неявно означает, что опрашивающий сервер поддерживает версию 2 протокола опрашивающего сервера и требуется начальная регистрация.</span><span class="sxs-lookup"><span data-stu-id="af125-186">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span>
<span data-ttu-id="af125-187">Наоборот, наличие свойства **ConfigurationID** означает, что используется версия 1 протокола опрашивающего сервера и регистрация не выполняется.</span><span class="sxs-lookup"><span data-stu-id="af125-187">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

><span data-ttu-id="af125-188">**Примечание**. В сценарии PUSH в текущем выпуске есть ошибка, из-за которой необходимо определять свойство ConfigurationID в файле метаконфигурации для узлов, которые никогда не регистрировались на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="af125-188">**Note**: In a PUSH scenario, a bug exists in the current release that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="af125-189">Это приведет к принудительному использованию версии 1 протокола опрашивающего сервера и позволит избежать сообщений об ошибках регистрации.</span><span class="sxs-lookup"><span data-stu-id="af125-189">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="af125-190">Размещение конфигураций и ресурсов</span><span class="sxs-lookup"><span data-stu-id="af125-190">Placing configurations and resources</span></span>

<span data-ttu-id="af125-191">После завершения установки опрашиваемого сервера папки для размещения модулей и конфигурации, которые будут доступны целевым узлам, задаются свойствами  **ConfigurationPath** и **ModulePath** в конфигурации опрашиваемого сервера.сервера.</span><span class="sxs-lookup"><span data-stu-id="af125-191">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span>
<span data-ttu-id="af125-192">Для правильной обработки опрашиваемым сервером эти файлы должны иметь специальный формат.</span><span class="sxs-lookup"><span data-stu-id="af125-192">These files need to be in a specific format in order for the pull server to correctly process them.</span></span>

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="af125-193">Формат пакета модуля для ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="af125-193">DSC resource module package format</span></span>

<span data-ttu-id="af125-194">Каждый модуль ресурса необходимо упаковать в ZIP-архив и переименовать согласно следующему шаблону: `{Module Name}_{Module Version}.zip`.</span><span class="sxs-lookup"><span data-stu-id="af125-194">Each resource module needs to be zipped and named according to the following pattern `{Module Name}_{Module Version}.zip`.</span></span>
<span data-ttu-id="af125-195">Например, модуль с именем xWebAdminstration с версией модуля 3.1.2.0 будет иметь имя "xWebAdministration_3.2.1.0.zip".</span><span class="sxs-lookup"><span data-stu-id="af125-195">For example, a module named xWebAdminstration with a module version of 3.1.2.0 would be named 'xWebAdministration_3.2.1.0.zip'.</span></span>
<span data-ttu-id="af125-196">Каждая версия модуля должна находиться в собственном ZIP-файле.</span><span class="sxs-lookup"><span data-stu-id="af125-196">Each version of a module must be contained in a single zip file.</span></span>
<span data-ttu-id="af125-197">Так как в каждом ZIP-файле существует только одна версия ресурса, формат модулей с поддержкой нескольких версий модуля в одном каталоге, который появился в WMF 5.0, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="af125-197">Since there is only a single version of a resource in each zip file, the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span>
<span data-ttu-id="af125-198">Это означает, что перед упаковкой модулей ресурсов DSC для опрашивающего сервера необходимо внести небольшое изменение в структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="af125-198">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span>
<span data-ttu-id="af125-199">Формат модулей, содержащих ресурсы DSC, в WMF 5.0 по умолчанию таков: "{папка_модуля}\{{версия_модуля}\DscResources\{{папка_ресурса_DSC}\'.</span><span class="sxs-lookup"><span data-stu-id="af125-199">The default format of modules containing DSC resource in WMF 5.0 is '{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\'.</span></span>
<span data-ttu-id="af125-200">Перед упаковкой для опрашиваемого сервера просто удалите папку **{версия_модуля}**, чтобы путь стал таким: "{папка_модуля}\DscResources\{{папка_ресурса_DSC}\'.</span><span class="sxs-lookup"><span data-stu-id="af125-200">Before packaging up for the pull server, remove the **{Module version}** folder so the path becomes '{Module Folder}\DscResources\{DSC Resource Folder}\'.</span></span>
<span data-ttu-id="af125-201">Выполнив это изменение, упакуйте папку в ZIP-архив, как описано выше, и поместите ZIP-архивы в папку **ModulePath**.</span><span class="sxs-lookup"><span data-stu-id="af125-201">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="af125-202">Используйте `New-DscChecksum {module zip file}`, чтобы создать файл контрольной суммы для только что добавленного модуля.</span><span class="sxs-lookup"><span data-stu-id="af125-202">Use `New-DscChecksum {module zip file}` to create a checksum file for the newly added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="af125-203">Формат файлов конфигурации MOF</span><span class="sxs-lookup"><span data-stu-id="af125-203">Configuration MOF format</span></span>

<span data-ttu-id="af125-204">MOF-файл конфигурации необходимо сопоставить с файлом контрольной суммы, чтобы LCM на целевом узле мог проверить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="af125-204">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span>
<span data-ttu-id="af125-205">Чтобы создать контрольную сумму, вызовите командлет [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DscChecksum).</span><span class="sxs-lookup"><span data-stu-id="af125-205">To create a checksum, call the [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DscChecksum) cmdlet.</span></span>
<span data-ttu-id="af125-206">Командлет принимает параметр **Path**, указывающий папку, в которой располагается MOF-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af125-206">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span>
<span data-ttu-id="af125-207">Командлет создает файл контрольной суммы `ConfigurationMOFName.mof.checksum`, где `ConfigurationMOFName` — имя MOF-файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af125-207">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span>
<span data-ttu-id="af125-208">Если в указанной папке есть несколько MOF-файлов конфигурации, контрольная сумма создается для каждой конфигурации в папке.</span><span class="sxs-lookup"><span data-stu-id="af125-208">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span>
<span data-ttu-id="af125-209">Поместите файлы MOF и их файлы контрольных сумм в папку **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="af125-209">Place the MOF files and their associated checksum files in the **ConfigurationPath** folder.</span></span>

><span data-ttu-id="af125-210">**Примечание**. Если вы измените MOF-файл конфигурации каким-либо образом, потребуется повторно создать файл контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="af125-210">**Note**: If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

### <a name="tooling"></a><span data-ttu-id="af125-211">Инструменты</span><span class="sxs-lookup"><span data-stu-id="af125-211">Tooling</span></span>

<span data-ttu-id="af125-212">Для упрощения настройки, проверки опрашиваемого сервера и управления им в последнюю версию модуля xPSDesiredStateConfiguration в качестве примеров включены следующие инструменты:
</span><span class="sxs-lookup"><span data-stu-id="af125-212">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>

1. <span data-ttu-id="af125-213">Модуль, который помогает упаковывать модули ресурсов и конфигурационные файлы DSC для использования на опрашиваемом сервере. </span><span class="sxs-lookup"><span data-stu-id="af125-213">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span> <span data-ttu-id="af125-214">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/master/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1).</span><span class="sxs-lookup"><span data-stu-id="af125-214">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/master/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1).</span></span> <span data-ttu-id="af125-215">Примеры ниже:</span><span class="sxs-lookup"><span data-stu-id="af125-215">Examples below:</span></span>

    ```powershell
        # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
         $moduleList = @('xWebAdministration', 'xPhp')
         Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList

         # Example 2 - Package modules and mof documents from c:\LocalDepot
         Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="af125-216">Сценарий, который проверяет, что опрашиваемый сервер настроен правильно.</span><span class="sxs-lookup"><span data-stu-id="af125-216">A script that validates the pull server is configured correctly.</span></span> <span data-ttu-id="af125-217">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/master/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1).</span><span class="sxs-lookup"><span data-stu-id="af125-217">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/master/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1).</span></span>

## <a name="community-solutions-for-pull-service"></a><span data-ttu-id="af125-218">Решения сообщества для опрашиваемой службы</span><span class="sxs-lookup"><span data-stu-id="af125-218">Community Solutions for Pull Service</span></span>

<span data-ttu-id="af125-219">Сообщество DSC разработало несколько решений для реализации протокола опрашиваемой службы.</span><span class="sxs-lookup"><span data-stu-id="af125-219">The DSC community has authored multiple solutions to implement the pull service protocol.</span></span>
<span data-ttu-id="af125-220">В случае локальных сред эти решения предоставляют функции опрашиваемой службы и дают возможность поделиться с сообществом своими улучшениями.</span><span class="sxs-lookup"><span data-stu-id="af125-220">For on-premises environments, these offer pull service capabilities and an opportunity to contribute back to the community with incremental enhancements.</span></span>

- [<span data-ttu-id="af125-221">Tug</span><span class="sxs-lookup"><span data-stu-id="af125-221">Tug</span></span>](https://github.com/powershellorg/tug)
- [<span data-ttu-id="af125-222">DSC-TRÆK</span><span class="sxs-lookup"><span data-stu-id="af125-222">DSC-TRÆK</span></span>](https://github.com/powershellorg/dsc-traek)

## <a name="pull-client-configuration"></a><span data-ttu-id="af125-223">Настройка опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="af125-223">Pull client configuration</span></span>

<span data-ttu-id="af125-224">В следующих разделах настройка опрашивающих клиентов описывается более подробно:</span><span class="sxs-lookup"><span data-stu-id="af125-224">The following topics describe setting up pull clients in detail:</span></span>

- [<span data-ttu-id="af125-225">Настройка опрашивающего клиента DSC с помощью идентификатора конфигурации</span><span class="sxs-lookup"><span data-stu-id="af125-225">Setting up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
- [<span data-ttu-id="af125-226">Настройка опрашивающего клиента DSC с помощью имен конфигурации</span><span class="sxs-lookup"><span data-stu-id="af125-226">Setting up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
- [<span data-ttu-id="af125-227">Частичные конфигурации</span><span class="sxs-lookup"><span data-stu-id="af125-227">Partial configurations</span></span>](partialConfigs.md)

## <a name="see-also"></a><span data-ttu-id="af125-228">См. также:</span><span class="sxs-lookup"><span data-stu-id="af125-228">See also</span></span>

- [<span data-ttu-id="af125-229">Общие сведения о службе настройки требуемого состояния Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af125-229">Windows PowerShell Desired State Configuration Overview</span></span>](overview.md)
- [<span data-ttu-id="af125-230">Активированные конфигурации</span><span class="sxs-lookup"><span data-stu-id="af125-230">Enacting configurations</span></span>](enactingConfigurations.md)
- [<span data-ttu-id="af125-231">Использование сервера отчетов DSC</span><span class="sxs-lookup"><span data-stu-id="af125-231">Using a DSC report server</span></span>](reportServer.md)