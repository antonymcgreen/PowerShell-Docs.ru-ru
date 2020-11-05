---
ms.date: 01/08/2020
keywords: dsc,powershell,конфигурация,установка
title: Опрашивающая служба DSC
description: Управление локальным диспетчером (LCM) конфигураций можно централизировать с помощью опрашиваемой службы. При использовании такого подхода управляемый узел регистрируется в службе, и ему в параметрах локального диспетчера конфигураций назначается конфигурация.
ms.openlocfilehash: 67d405deda23569964e5eb401a4405a584369430
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92659124"
---
# <a name="desired-state-configuration-pull-service"></a><span data-ttu-id="4d153-105">Опрашивающая служба Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="4d153-105">Desired State Configuration Pull Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d153-106">Опрашивающий сервер (компонент Windows *служба DSC* ) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="4d153-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="4d153-107">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="4d153-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="4d153-108">Управление локальным диспетчером (LCM) конфигураций можно централизировать с помощью опрашиваемой службы.</span><span class="sxs-lookup"><span data-stu-id="4d153-108">Local Configuration Manager (LCM) can be centrally managed by a Pull Service solution.</span></span> <span data-ttu-id="4d153-109">При использовании такого подхода управляемый узел регистрируется в службе, и ему в параметрах локального диспетчера конфигураций назначается конфигурация.</span><span class="sxs-lookup"><span data-stu-id="4d153-109">When using this approach, the node that is being managed is registered with a service and assigned a configuration in LCM settings.</span></span> <span data-ttu-id="4d153-110">Конфигурация и все ресурсы DSC, которые необходимы в качестве зависимостей конфигурации, загружаются на компьютер и используются локальным диспетчером конфигураций для управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="4d153-110">The configuration and all DSC resources needed as dependencies for the configuration are downloaded to the machine and used by LCM to manage the configuration.</span></span>
<span data-ttu-id="4d153-111">Сведения о состоянии управляемого компьютера отправляются в службу для отчетности.</span><span class="sxs-lookup"><span data-stu-id="4d153-111">Information about the state of the machine being managed is uploaded to the service for reporting.</span></span>
<span data-ttu-id="4d153-112">Эта концепция называется "опрашивающей службой".</span><span class="sxs-lookup"><span data-stu-id="4d153-112">This concept is referred to as "pull service".</span></span>

<span data-ttu-id="4d153-113">Текущие варианты опрашиваемой службы:</span><span class="sxs-lookup"><span data-stu-id="4d153-113">The current options for pull service include:</span></span>

- <span data-ttu-id="4d153-114">служба Desired State Configuration в службе автоматизации Azure;</span><span class="sxs-lookup"><span data-stu-id="4d153-114">Azure Automation Desired State Configuration service</span></span>
- <span data-ttu-id="4d153-115">Опрашиваемая служба в Windows Server</span><span class="sxs-lookup"><span data-stu-id="4d153-115">A pull service running on Windows Server</span></span>
- <span data-ttu-id="4d153-116">Решения с открытым исходным кодом, поддерживаемые сообществом</span><span class="sxs-lookup"><span data-stu-id="4d153-116">Community maintained open-source solutions</span></span>
- <span data-ttu-id="4d153-117">Общий ресурс SMB</span><span class="sxs-lookup"><span data-stu-id="4d153-117">An SMB share</span></span>

<span data-ttu-id="4d153-118">Для каждого решения рекомендуется использовать следующий масштаб:</span><span class="sxs-lookup"><span data-stu-id="4d153-118">The recommended scale for each solution is as follows:</span></span>

|                   <span data-ttu-id="4d153-119">Решение</span><span class="sxs-lookup"><span data-stu-id="4d153-119">Solution</span></span>                   |              <span data-ttu-id="4d153-120">Клиентские узлы</span><span class="sxs-lookup"><span data-stu-id="4d153-120">Client nodes</span></span>              |
| -------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="4d153-121">Опрашивающий сервер Windows, использующий базу данных MDB или ESENT</span><span class="sxs-lookup"><span data-stu-id="4d153-121">Windows Pull Server using MDB/ESENT database</span></span> | <span data-ttu-id="4d153-122">До 500 узлов</span><span class="sxs-lookup"><span data-stu-id="4d153-122">Up to 500 nodes</span></span>                        |
| <span data-ttu-id="4d153-123">Опрашивающий сервер Windows, использующий базу данных SQL</span><span class="sxs-lookup"><span data-stu-id="4d153-123">Windows Pull Server using SQL database</span></span>       | <span data-ttu-id="4d153-124">До 3500 узлов</span><span class="sxs-lookup"><span data-stu-id="4d153-124">Up to 3500 nodes</span></span>                       |
| <span data-ttu-id="4d153-125">DSC службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="4d153-125">Azure Automation DSC</span></span>                         | <span data-ttu-id="4d153-126">Малые и большие среды</span><span class="sxs-lookup"><span data-stu-id="4d153-126">Both small and large environments</span></span>      |

<span data-ttu-id="4d153-127">**Рекомендуемое решение** и вариант с наибольшим числом доступных функций — [DSC в службе автоматизации Azure](/azure/automation/automation-dsc-getting-started).</span><span class="sxs-lookup"><span data-stu-id="4d153-127">**The recommended solution** , and the option with the most features available, is [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span> <span data-ttu-id="4d153-128">Не определен верхний предел количества узлов на учетную запись службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="4d153-128">An upper limit for number of nodes per Automation Account has not been identified.</span></span>

<span data-ttu-id="4d153-129">Служба Azure может управлять узлами в локальных частных центрах обработки данных или в общедоступных облаках, таких как Azure и AWS.</span><span class="sxs-lookup"><span data-stu-id="4d153-129">The Azure service can manage nodes on-premises in private datacenters, or in public clouds such as Azure and AWS.</span></span> <span data-ttu-id="4d153-130">Для частных сред, где серверы не могут напрямую подключаться к Интернету, рекомендуем ограничить исходящий трафик только опубликованным диапазоном IP-адресов Azure (см. сведения о [диапазонах IP-адресов для центров обработки данных Azure](https://www.microsoft.com/download/details.aspx?id=41653)).</span><span class="sxs-lookup"><span data-stu-id="4d153-130">For private environments where servers cannot directly connect to the Internet, consider limiting outbound traffic to only the published Azure IP range (see [Azure Datacenter IP Ranges](https://www.microsoft.com/download/details.aspx?id=41653)).</span></span>

<span data-ttu-id="4d153-131">Функции веб-службы, которые сейчас недоступны в опрашиваемой службе в Windows Server:</span><span class="sxs-lookup"><span data-stu-id="4d153-131">Features of the online service that are not currently available in the pull service on Windows Server include:</span></span>

- <span data-ttu-id="4d153-132">Шифрование всех данных при передаче и хранении.</span><span class="sxs-lookup"><span data-stu-id="4d153-132">All data is encrypted in transit and at rest</span></span>
- <span data-ttu-id="4d153-133">Автоматическое создание и обслуживание клиентских сертификатов.</span><span class="sxs-lookup"><span data-stu-id="4d153-133">Client certificates are created and managed automatically</span></span>
- <span data-ttu-id="4d153-134">Хранение секретов с централизованным управлением [паролями и учетными данными](/azure/automation/automation-credentials) или [переменными](/azure/automation/automation-variables), такими как имена серверов или строки подключения.</span><span class="sxs-lookup"><span data-stu-id="4d153-134">Secrets store for centrally managing [passwords/credentials](/azure/automation/automation-credentials), or [variables](/azure/automation/automation-variables) such as server names or connection strings</span></span>
- <span data-ttu-id="4d153-135">Централизованное управление [конфигурацией LCM](../managing-nodes/metaConfig.md#basic-settings) в узле.</span><span class="sxs-lookup"><span data-stu-id="4d153-135">Centrally manage node [LCM configuration](../managing-nodes/metaConfig.md#basic-settings)</span></span>
- <span data-ttu-id="4d153-136">Централизованное назначение конфигураций клиентским узлам.</span><span class="sxs-lookup"><span data-stu-id="4d153-136">Centrally assign configurations to client nodes</span></span>
- <span data-ttu-id="4d153-137">Выпуск изменений конфигурации для небольших групп пользователей, позволяющий протестировать решение перед реализацией в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="4d153-137">Release configuration changes to "canary groups" for testing before reaching production</span></span>
- <span data-ttu-id="4d153-138">Графические отчеты:</span><span class="sxs-lookup"><span data-stu-id="4d153-138">Graphical reporting</span></span>
  - <span data-ttu-id="4d153-139">сведения о состоянии на уровне ресурсов DSC;</span><span class="sxs-lookup"><span data-stu-id="4d153-139">Status detail at the DSC resource level of granularity</span></span>
  - <span data-ttu-id="4d153-140">подробные сообщения об ошибках с клиентских компьютеров для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="4d153-140">Verbose error messages from client machines for troubleshooting</span></span>
- <span data-ttu-id="4d153-141">[Интеграция с Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) для отправки предупреждений, автоматизации задач, а также выполнения приложений Android или iOS для создания отчетов и оповещений.</span><span class="sxs-lookup"><span data-stu-id="4d153-141">[Integration with Azure Log Analytics](/azure/automation/automation-dsc-diagnostics) for alerting, automated tasks, Android/iOS app for reporting and alerting</span></span>

## <a name="dsc-pull-service-in-windows-server"></a><span data-ttu-id="4d153-142">Опрашиваемая служба DSC в Windows Server</span><span class="sxs-lookup"><span data-stu-id="4d153-142">DSC pull service in Windows Server</span></span>

<span data-ttu-id="4d153-143">Опрашиваемую службу можно настроить для работы в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4d153-143">It is possible to configure a pull service to run on Windows Server.</span></span> <span data-ttu-id="4d153-144">Учтите, что решение опрашиваемой службы в составе Windows Server включает только возможности хранения конфигураций и модулей для скачивания и записи данных отчетов в базу данных.</span><span class="sxs-lookup"><span data-stu-id="4d153-144">Be advised that the pull service solution included in Windows Server includes only capabilities of storing configurations and modules for download and capturing report data into a database.</span></span> <span data-ttu-id="4d153-145">Она не включает многих функций, предоставляемых службой в Azure, и поэтому не совсем подходит для оценки потенциального использования службы.</span><span class="sxs-lookup"><span data-stu-id="4d153-145">It does not include many of the capabilities offered by the service in Azure and so, is not a good tool for evaluating how the service would be used.</span></span>

<span data-ttu-id="4d153-146">Опрашиваемая служба в Windows Server — это веб-служба в составе IIS, которая использует интерфейс OData для создания файлов конфигурации DSC, доступных целевым узлам по запросу.</span><span class="sxs-lookup"><span data-stu-id="4d153-146">The pull service offered in Windows Server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="4d153-147">Требования к использованию опрашиваемого сервера:</span><span class="sxs-lookup"><span data-stu-id="4d153-147">Requirements for using a pull server:</span></span>

- <span data-ttu-id="4d153-148">Сервер под управлением:</span><span class="sxs-lookup"><span data-stu-id="4d153-148">A server running:</span></span>
  - <span data-ttu-id="4d153-149">WMF/PowerShell 4.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="4d153-149">WMF/PowerShell 4.0 or greater</span></span>
  - <span data-ttu-id="4d153-150">Роль сервера служб IIS</span><span class="sxs-lookup"><span data-stu-id="4d153-150">IIS server role</span></span>
  - <span data-ttu-id="4d153-151">Служба DSC</span><span class="sxs-lookup"><span data-stu-id="4d153-151">DSC Service</span></span>
- <span data-ttu-id="4d153-152">Рекомендуется использовать средства создания сертификата для защиты учетных данных, передаваемых в локальный диспетчер конфигураций (LCM) на целевых узлах</span><span class="sxs-lookup"><span data-stu-id="4d153-152">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="4d153-153">Для настройки размещения опрашиваемой службы в Windows Server лучше всего воспользоваться конфигурацией DSC.</span><span class="sxs-lookup"><span data-stu-id="4d153-153">The best way to configure Windows Server to host pull service is to use a DSC configuration.</span></span> <span data-ttu-id="4d153-154">Пример сценария приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="4d153-154">An example script is provided below.</span></span>

### <a name="supported-database-systems"></a><span data-ttu-id="4d153-155">Поддерживаемые системы баз данных</span><span class="sxs-lookup"><span data-stu-id="4d153-155">Supported database systems</span></span>

| <span data-ttu-id="4d153-156">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="4d153-156">WMF 4.0</span></span> |       <span data-ttu-id="4d153-157">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="4d153-157">WMF 5.0</span></span>        |       <span data-ttu-id="4d153-158">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="4d153-158">WMF 5.1</span></span>        | <span data-ttu-id="4d153-159">WMF 5.1 (Windows Server Insider Preview версии 17090)</span><span class="sxs-lookup"><span data-stu-id="4d153-159">WMF 5.1 (Windows Server Insider Preview 17090)</span></span> |
| ------- | -------------------- | -------------------- | ---------------------------------------------- |
| <span data-ttu-id="4d153-160">MDB</span><span class="sxs-lookup"><span data-stu-id="4d153-160">MDB</span></span>     | <span data-ttu-id="4d153-161">ESENT (по умолчанию), MDB</span><span class="sxs-lookup"><span data-stu-id="4d153-161">ESENT (Default), MDB</span></span> | <span data-ttu-id="4d153-162">ESENT (по умолчанию), MDB</span><span class="sxs-lookup"><span data-stu-id="4d153-162">ESENT (Default), MDB</span></span> | <span data-ttu-id="4d153-163">ESENT (по умолчанию), SQL Server, MDB</span><span class="sxs-lookup"><span data-stu-id="4d153-163">ESENT (Default), SQL Server, MDB</span></span>               |

<span data-ttu-id="4d153-164">Начиная с выпуска Windows Server 17090 в опрашивающей службе (компонент Windows *служба DSC* ) поддерживается SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d153-164">Starting in release 17090 of Windows Server, SQL Server is a supported option for the Pull Service (Windows Feature *DSC-Service* ).</span></span> <span data-ttu-id="4d153-165">Это новый вариант масштабирования крупных сред DSC, которые не были перенесены в [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span><span class="sxs-lookup"><span data-stu-id="4d153-165">This provides a new option for scaling large DSC environments that have not migrated to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started).</span></span>

> [!NOTE]
> <span data-ttu-id="4d153-166">Поддержка SQL Server не будет добавлена в предыдущие версии WMF 5.1 (или более ранние версии) и будет доступна только в Windows Server версии 17090 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="4d153-166">SQL Server support will not be added to previous versions of WMF 5.1 (or earlier) and will only be available on Windows Server versions greater than or equal to 17090.</span></span>

<span data-ttu-id="4d153-167">Чтобы настроить на опрашивающем сервере использование SQL Server, установите значение `$true` для параметра **SqlProvider** и допустимую строку подключения SQL Server для параметра **SqlConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="4d153-167">To configure the pull server to use SQL Server, set **SqlProvider** to `$true` and **SqlConnectionString** to a valid SQL Server Connection String.</span></span> <span data-ttu-id="4d153-168">Дополнительные сведения см. в разделе [Строки подключения SqlClient](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span><span class="sxs-lookup"><span data-stu-id="4d153-168">For more information, see [SqlClient Connection Strings](/dotnet/framework/data/adonet/connection-string-syntax#sqlclient-connection-strings).</span></span>
<span data-ttu-id="4d153-169">Чтобы ознакомиться с настройкой SQL Server с помощью **xDscWebService** , прочтите статью [Использование ресурса xDscWebService](#using-the-xdscwebservice-resource) и просмотрите файл [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 в GitHub](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span><span class="sxs-lookup"><span data-stu-id="4d153-169">For an example of SQL Server configuration with **xDscWebService** , first read [Using the xDscWebService resource](#using-the-xdscwebservice-resource) and then review [Sample_xDscWebServiceRegistration_UseSQLProvider.ps1 on GitHub](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Examples/Sample_xDscWebServiceRegistration_UseSQLProvider.ps1).</span></span>

### <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="4d153-170">Использование ресурса xDSCWebService</span><span class="sxs-lookup"><span data-stu-id="4d153-170">Using the xDscWebService resource</span></span>

<span data-ttu-id="4d153-171">Самый простой способ настроить опрашиваемый веб-сервер — использовать ресурс **xDscWebService** , включенный в модуль **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4d153-171">The easiest way to set up a web pull server is to use the **xDscWebService** resource, included in the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="4d153-172">В следующих действиях показано, как использовать ресурс в скрипте `Configuration`, используемом для настройки веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4d153-172">The following steps explain how to use the resource in a `Configuration` that sets up the web service.</span></span>

1. <span data-ttu-id="4d153-173">Вызовите командлет [Install-Module](/powershell/module/PowerShellGet/Install-Module), чтобы установить модуль **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4d153-173">Call the [Install-Module](/powershell/module/PowerShellGet/Install-Module) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4d153-174">`Install-Module` включен в модуль **PowerShellGet** , содержащийся в PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4d153-174">`Install-Module` is included in the **PowerShellGet** module, which is included in PowerShell 5.0 and higher.</span></span>

1. <span data-ttu-id="4d153-175">Получите SSL-сертификат для опрашивающего сервера DSC из доверенного центра сертификации (общедоступного или входящего в состав вашей организации). </span><span class="sxs-lookup"><span data-stu-id="4d153-175">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="4d153-176">Полученный из центра сертификат обычно имеет формат PFX.</span><span class="sxs-lookup"><span data-stu-id="4d153-176">The certificate received from the authority is usually in the PFX format.</span></span>
1. <span data-ttu-id="4d153-177">Установите сертификат на узле, который должен стать опрашиваемым сервером DSC, в расположении по умолчанию (`CERT:\LocalMachine\My`).</span><span class="sxs-lookup"><span data-stu-id="4d153-177">Install the certificate on the node that will become the DSC Pull server in the default location, which should be `CERT:\LocalMachine\My`.</span></span>
   - <span data-ttu-id="4d153-178">Запишите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="4d153-178">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="4d153-179">Выберите идентификатор GUID для использования в качестве ключа регистрации.</span><span class="sxs-lookup"><span data-stu-id="4d153-179">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="4d153-180">Чтобы создать его с помощью PowerShell, в командной строке PS введите следующее и нажмите клавишу ВВОД: `[guid]::newGuid()` или `New-Guid`.</span><span class="sxs-lookup"><span data-stu-id="4d153-180">To generate one using PowerShell enter the following at the PS prompt and press enter: `[guid]::newGuid()` or `New-Guid`.</span></span> <span data-ttu-id="4d153-181">Этот ключ будет использоваться клиентскими узлами в качестве общего ключа для проверки подлинности во время регистрации.</span><span class="sxs-lookup"><span data-stu-id="4d153-181">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="4d153-182">Дополнительные сведения см. в разделе "Ключ регистрации" ниже.</span><span class="sxs-lookup"><span data-stu-id="4d153-182">For more information, see the Registration Key section below.</span></span>
1. <span data-ttu-id="4d153-183">В ISE PowerShell запустите (нажав клавишу <kbd>F5</kbd>) следующий скрипт конфигурации (включенный в пример папки модуля **xPSDesiredStateConfiguration** в качестве `Sample_xDscWebServiceRegistration.ps1`).</span><span class="sxs-lookup"><span data-stu-id="4d153-183">In the PowerShell ISE, start ( <kbd>F5</kbd>) the following configuration script (included in the folder of the **xPSDesiredStateConfiguration** module as `Sample_xDscWebServiceRegistration.ps1`) .</span></span> <span data-ttu-id="4d153-184">Этот сценарий настраивает опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="4d153-184">This script sets up the pull server.</span></span>

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

        Import-DSCResource -ModuleName PSDesiredStateConfiguration
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
                UseSecurityBestPractices     = $true
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

1. <span data-ttu-id="4d153-185">Запустите конфигурацию, передав отпечаток SSL-сертификата с параметром **certificateThumbPrint** и ключ регистрации GUID с параметром **RegistrationKey** :</span><span class="sxs-lookup"><span data-stu-id="4d153-185">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

    ```powershell
    # To find the Thumbprint for an installed SSL certificate for use with the pull server list all
    # certificates in your local store and then copy the thumbprint for the appropriate certificate
    # by     reviewing the certificate subjects

    dir Cert:\LocalMachine\my

    # Then include this thumbprint when running the configuration
    Sample_xDscWebServiceRegistration -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

    # Run the compiled configuration to make the target node a DSC Pull Server
    Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose
    ```

#### <a name="registration-key"></a><span data-ttu-id="4d153-186">Ключ регистрации</span><span class="sxs-lookup"><span data-stu-id="4d153-186">Registration Key</span></span>

<span data-ttu-id="4d153-187">Чтобы разрешить клиентским узлам регистрироваться на сервере для использования имен конфигурации вместо идентификаторов конфигурации, созданный конфигурацией ключ сохраняется в файле `RegistrationKeys.txt` в `C:\Program Files\WindowsPowerShell\DscService`.</span><span class="sxs-lookup"><span data-stu-id="4d153-187">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key that was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="4d153-188">Ключ регистрации работает как общий секрет, используемый во время первоначальной регистрации клиента с опрашиваемым сервером.</span><span class="sxs-lookup"><span data-stu-id="4d153-188">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="4d153-189">Клиент создает самозаверяющий сертификат, который используется для уникальной проверки подлинности на опрашиваемом сервере после успешного завершения регистрации.</span><span class="sxs-lookup"><span data-stu-id="4d153-189">The client will generate a self-signed certificate that is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="4d153-190">Отпечаток этого сертификата сохраняется локально и связывается с URL-адресом опрашиваемого сервера.</span><span class="sxs-lookup"><span data-stu-id="4d153-190">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="4d153-191">Ключи регистрации не поддерживаются в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="4d153-191">Registration keys are not supported in PowerShell 4.0.</span></span>

<span data-ttu-id="4d153-192">Для настройки проверки подлинности узла опрашиваемом сервере необходимо поместить ключ регистрации в метаконфигурацию всех целевых узлов, которые будут регистрироваться на этом опрашиваемом сервере.</span><span class="sxs-lookup"><span data-stu-id="4d153-192">In order to configure a node to authenticate with the pull server, the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="4d153-193">Обратите внимание, что **RegistrationKey** в метаконфигурации ниже удаляется после успешной регистрации целевого компьютера, и значение должно соответствовать значению в файле `RegistrationKeys.txt` на опрашиваемом сервере (в этом примере — "140a952b-b9d6-406b-b416-e0f759c9c0e4").</span><span class="sxs-lookup"><span data-stu-id="4d153-193">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value must match the value stored in the `RegistrationKeys.txt` file on the pull server ('140a952b-b9d6-406b-b416-e0f759c9c0e4' for this example).</span></span> <span data-ttu-id="4d153-194">Значение ключа регистрации должно оставаться конфиденциальным, так как с ним любой целевой компьютер сможет зарегистрироваться на опрашиваемом сервере.</span><span class="sxs-lookup"><span data-stu-id="4d153-194">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration Sample_MetaConfigurationToRegisterWithLessSecurePullServer
{
    param
    (
        [ValidateNotNullOrEmpty()]
        [string] $NodeName = 'localhost',

        [ValidateNotNullOrEmpty()]
        [string] $RegistrationKey, #same as the one used to set up pull server in previous configuration

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

> [!NOTE]
> <span data-ttu-id="4d153-195">Раздел **ReportServerWeb** позволяет отправлять данные отчетов на опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="4d153-195">The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span>

<span data-ttu-id="4d153-196">Отсутствие свойства **ConfigurationID** в файле метаконфигурации неявно означает, что опрашивающий сервер поддерживает версию 2 протокола опрашивающего сервера и требуется начальная регистрация.</span><span class="sxs-lookup"><span data-stu-id="4d153-196">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span> <span data-ttu-id="4d153-197">Наоборот, наличие свойства **ConfigurationID** означает, что используется версия 1 протокола опрашиваемого сервера и регистрация не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4d153-197">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

> [!NOTE]
> <span data-ttu-id="4d153-198">В сценарии PUSH в текущем выпуске есть ошибка, из-за которой необходимо определять свойство ConfigurationID в файле метаконфигурации для узлов, которые никогда не регистрировались на опрашиваемом сервере.</span><span class="sxs-lookup"><span data-stu-id="4d153-198">In a PUSH scenario, a bug exists in the current release that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="4d153-199">Это приведет к принудительному использованию версии 1 протокола опрашиваемого сервера и позволит избежать сообщений об ошибках регистрации.</span><span class="sxs-lookup"><span data-stu-id="4d153-199">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="4d153-200">Размещение конфигураций и ресурсов</span><span class="sxs-lookup"><span data-stu-id="4d153-200">Placing configurations and resources</span></span>

<span data-ttu-id="4d153-201">После завершения установки опрашивающего сервера папки для размещения модулей и конфигурации, которые будут доступны целевым узлам, задаются свойствами **ConfigurationPath** и **ModulePath** в конфигурации опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="4d153-201">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span> <span data-ttu-id="4d153-202">Для правильной обработки опрашиваемым сервером эти файлы должны иметь специальный формат.</span><span class="sxs-lookup"><span data-stu-id="4d153-202">These files need to be in a specific format in order for the pull server to correctly process them.</span></span>

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="4d153-203">Формат пакета модуля для ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="4d153-203">DSC resource module package format</span></span>

<span data-ttu-id="4d153-204">Каждый модуль ресурса необходимо упаковать в ZIP-архив и переименовать согласно следующему шаблону: `{Module Name}_{Module Version}.zip`.</span><span class="sxs-lookup"><span data-stu-id="4d153-204">Each resource module needs to be zipped and named according to the following pattern `{Module Name}_{Module Version}.zip`.</span></span>

<span data-ttu-id="4d153-205">Например, модуль с именем **xWebAdminstration** с версией модуля 3.1.2.0 будет иметь имя `xWebAdministration_3.1.2.0.zip`.</span><span class="sxs-lookup"><span data-stu-id="4d153-205">For example, a module named **xWebAdminstration** with a module version of 3.1.2.0 would be named `xWebAdministration_3.1.2.0.zip`.</span></span> <span data-ttu-id="4d153-206">Каждая версия модуля должна находиться в собственном ZIP-файле.</span><span class="sxs-lookup"><span data-stu-id="4d153-206">Each version of a module must be contained in a single zip file.</span></span>
<span data-ttu-id="4d153-207">Так как в каждом ZIP-файле существует только одна версия ресурса, формат модулей с поддержкой нескольких версий модуля в одном каталоге, который появился в WMF 5.0, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4d153-207">Since there is only a single version of a resource in each zip file, the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span> <span data-ttu-id="4d153-208">Это означает, что перед упаковкой модулей ресурсов DSC для опрашиваемого сервера необходимо внести небольшое изменение в структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="4d153-208">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span> <span data-ttu-id="4d153-209">Формат модулей, содержащих ресурсы DSC, в WMF 5.0 по умолчанию таков: `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span><span class="sxs-lookup"><span data-stu-id="4d153-209">The default format of modules containing DSC resource in WMF 5.0 is `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="4d153-210">Перед упаковкой для опрашиваемого сервера удалите папку **{Module version}** , чтобы путь стал таким: `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span><span class="sxs-lookup"><span data-stu-id="4d153-210">Before packaging up for the pull server, remove the **{Module version}** folder so the path becomes `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="4d153-211">Выполнив это изменение, упакуйте папку в ZIP-архив, как описано выше, и поместите ZIP-архивы в папку **ModulePath**.</span><span class="sxs-lookup"><span data-stu-id="4d153-211">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="4d153-212">Используйте `New-DscChecksum {module zip file}`, чтобы создать файл контрольной суммы для только что добавленного модуля.</span><span class="sxs-lookup"><span data-stu-id="4d153-212">Use `New-DscChecksum {module zip file}` to create a checksum file for the newly added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="4d153-213">Формат файлов конфигурации MOF</span><span class="sxs-lookup"><span data-stu-id="4d153-213">Configuration MOF format</span></span>

<span data-ttu-id="4d153-214">MOF-файл конфигурации необходимо сопоставить с файлом контрольной суммы, чтобы LCM на целевом узле мог проверить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="4d153-214">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="4d153-215">Чтобы создать контрольную сумму, вызовите командлет [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum).</span><span class="sxs-lookup"><span data-stu-id="4d153-215">To create a checksum, call the [New-DscChecksum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet.</span></span> <span data-ttu-id="4d153-216">Командлет принимает параметр **Path** , указывающий папку, в которой располагается MOF-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d153-216">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="4d153-217">Командлет создает файл контрольной суммы `ConfigurationMOFName.mof.checksum`, где `ConfigurationMOFName` — имя MOF-файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d153-217">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="4d153-218">Если в указанной папке есть несколько MOF-файлов конфигурации, контрольная сумма создается для каждой конфигурации в папке.</span><span class="sxs-lookup"><span data-stu-id="4d153-218">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span> <span data-ttu-id="4d153-219">Поместите файлы MOF и их файлы контрольных сумм в папку **ConfigurationPath**.</span><span class="sxs-lookup"><span data-stu-id="4d153-219">Place the MOF files and their associated checksum files in the **ConfigurationPath** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="4d153-220">Если вы измените MOF-файл конфигурации каким-либо образом, потребуется повторно создать файл контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="4d153-220">If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

### <a name="tooling"></a><span data-ttu-id="4d153-221">Инструментарий</span><span class="sxs-lookup"><span data-stu-id="4d153-221">Tooling</span></span>

<span data-ttu-id="4d153-222">Для упрощения настройки, проверки опрашиваемого сервера и управления им в последнюю версию модуля xPSDesiredStateConfiguration в качестве примеров включены следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="4d153-222">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>

1. <span data-ttu-id="4d153-223">Модуль, который помогает упаковывать модули ресурсов и конфигурационные файлы DSC для использования на опрашиваемом сервере. </span><span class="sxs-lookup"><span data-stu-id="4d153-223">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span>
   <span data-ttu-id="4d153-224">[PublishModulesAndMofsToPullServer.psm1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetup.psm1).</span><span class="sxs-lookup"><span data-stu-id="4d153-224">[PublishModulesAndMofsToPullServer.psm1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetup.psm1).</span></span>
   <span data-ttu-id="4d153-225">Примеры ниже:</span><span class="sxs-lookup"><span data-stu-id="4d153-225">Examples below:</span></span>

    ```powershell
    # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
    $moduleList = @('xWebAdministration', 'xPhp')
    Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList

    # Example 2 - Package modules and mof documents from c:\LocalDepot
    Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="4d153-226">Сценарий, который проверяет, что опрашиваемый сервер настроен правильно.</span><span class="sxs-lookup"><span data-stu-id="4d153-226">A script that validates the pull server is configured correctly.</span></span>
   <span data-ttu-id="4d153-227">[PullServerSetupTests.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetupTest/DscPullServerSetupTest.ps1).</span><span class="sxs-lookup"><span data-stu-id="4d153-227">[PullServerSetupTests.ps1](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/Modules/DscPullServerSetup/DscPullServerSetupTest/DscPullServerSetupTest.ps1).</span></span>

## <a name="community-solutions-for-pull-service"></a><span data-ttu-id="4d153-228">Решения сообщества для опрашиваемой службы</span><span class="sxs-lookup"><span data-stu-id="4d153-228">Community Solutions for Pull Service</span></span>

<span data-ttu-id="4d153-229">Сообщество DSC разработало несколько решений для реализации протокола опрашиваемой службы.</span><span class="sxs-lookup"><span data-stu-id="4d153-229">The DSC community has authored multiple solutions to implement the pull service protocol.</span></span> <span data-ttu-id="4d153-230">В случае локальных сред эти решения предоставляют функции опрашиваемой службы и дают возможность поделиться с сообществом своими улучшениями.</span><span class="sxs-lookup"><span data-stu-id="4d153-230">For on-premises environments, these offer pull service capabilities and an opportunity to contribute back to the community with incremental enhancements.</span></span>

- [<span data-ttu-id="4d153-231">Tug</span><span class="sxs-lookup"><span data-stu-id="4d153-231">Tug</span></span>](https://github.com/powershellorg/tug)
- [<span data-ttu-id="4d153-232">DSC-TRÆK</span><span class="sxs-lookup"><span data-stu-id="4d153-232">DSC-TRÆK</span></span>](https://github.com/powershellorg/dsc-traek)

## <a name="pull-client-configuration"></a><span data-ttu-id="4d153-233">Настройка опрашивающего клиента</span><span class="sxs-lookup"><span data-stu-id="4d153-233">Pull client configuration</span></span>

<span data-ttu-id="4d153-234">В следующих разделах настройка опрашивающих клиентов описывается более подробно:</span><span class="sxs-lookup"><span data-stu-id="4d153-234">The following topics describe setting up pull clients in detail:</span></span>

- [<span data-ttu-id="4d153-235">Настройка опрашивающего клиента DSC с помощью идентификатора конфигурации</span><span class="sxs-lookup"><span data-stu-id="4d153-235">Set up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
- [<span data-ttu-id="4d153-236">Настройка опрашивающего клиента DSC с помощью имен конфигурации</span><span class="sxs-lookup"><span data-stu-id="4d153-236">Set up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
- [<span data-ttu-id="4d153-237">Частичные конфигурации</span><span class="sxs-lookup"><span data-stu-id="4d153-237">Partial configurations</span></span>](partialConfigs.md)

## <a name="see-also"></a><span data-ttu-id="4d153-238">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4d153-238">See also</span></span>

- [<span data-ttu-id="4d153-239">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="4d153-239">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="4d153-240">Применение конфигураций</span><span class="sxs-lookup"><span data-stu-id="4d153-240">Enacting configurations</span></span>](enactingConfigurations.md)
- [<span data-ttu-id="4d153-241">Использование сервера отчетов DSC</span><span class="sxs-lookup"><span data-stu-id="4d153-241">Using a DSC report server</span></span>](reportServer.md)
- <span data-ttu-id="4d153-242">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol](/openspecs/windows_protocols/ms-dscpm/ea744c01-51a2-4000-9ef2-312711dcc8c9) (MS-DSCPM: Требуемое состояние конфигурации протокола с активным опросом сообщений)</span><span class="sxs-lookup"><span data-stu-id="4d153-242">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol](/openspecs/windows_protocols/ms-dscpm/ea744c01-51a2-4000-9ef2-312711dcc8c9)</span></span>
- <span data-ttu-id="4d153-243">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol](/openspecs/windows_protocols/ms-winerrata/f5fc7ae3-9172-41e8-ac6a-2a5a5b7bfaf5) (MS-DSCPM: Требуемое состояние конфигурации протокола с активным опросом сообщений об ошибке)</span><span class="sxs-lookup"><span data-stu-id="4d153-243">[[MS-DSCPM]: Desired State Configuration Pull Model Protocol Errata](/openspecs/windows_protocols/ms-winerrata/f5fc7ae3-9172-41e8-ac6a-2a5a5b7bfaf5)</span></span>
