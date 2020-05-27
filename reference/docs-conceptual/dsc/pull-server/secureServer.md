---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Рекомендации по опрашивающим серверам
ms.openlocfilehash: 2d707dc64c327cf30d09104aee140e5b78ee7c29
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692253"
---
# <a name="pull-server-best-practices"></a><span data-ttu-id="9dc81-103">Рекомендации по опрашивающим серверам</span><span class="sxs-lookup"><span data-stu-id="9dc81-103">Pull server best practices</span></span>

<span data-ttu-id="9dc81-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9dc81-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dc81-105">Опрашивающий сервер (компонент Windows *служба DSC*) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется.</span><span class="sxs-lookup"><span data-stu-id="9dc81-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="9dc81-106">Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).</span><span class="sxs-lookup"><span data-stu-id="9dc81-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="9dc81-107">Сводка. в этом документе описываются процессы и действия, которые могут быть полезны для инженеров, готовящихся к развертыванию решения.</span><span class="sxs-lookup"><span data-stu-id="9dc81-107">Summary: This document is intended to include process and extensibility to assist engineers who are preparing for the solution.</span></span> <span data-ttu-id="9dc81-108">Информация в документе содержит в себе рекомендации, изложенные клиентами и затем проверенные рабочей группой по продукту, что позволяет гарантировать их перспективность и стабильность.</span><span class="sxs-lookup"><span data-stu-id="9dc81-108">Details should provide best practices as identified by customers and then validated by the product team to ensure recommendations are future facing and considered stable.</span></span>

|           |                      <span data-ttu-id="9dc81-109">Информация о документе</span><span class="sxs-lookup"><span data-stu-id="9dc81-109">Doc Info</span></span>                      |
| :-------- | :------------------------------------------------- |
| <span data-ttu-id="9dc81-110">Автор</span><span class="sxs-lookup"><span data-stu-id="9dc81-110">Author</span></span>    | <span data-ttu-id="9dc81-111">Майкл Грин (Michael Greene)</span><span class="sxs-lookup"><span data-stu-id="9dc81-111">Michael Greene</span></span>                                     |
| <span data-ttu-id="9dc81-112">Рецензенты</span><span class="sxs-lookup"><span data-stu-id="9dc81-112">Reviewers</span></span> | <span data-ttu-id="9dc81-113">Бен Геленс (Ben Gelens), Равикант Чаганти (Ravikanth Chaganti), Александар Николич (Aleksandar Nikolic)</span><span class="sxs-lookup"><span data-stu-id="9dc81-113">Ben Gelens, Ravikanth Chaganti, Aleksandar Nikolic</span></span> |
| <span data-ttu-id="9dc81-114">Опубликован</span><span class="sxs-lookup"><span data-stu-id="9dc81-114">Published</span></span> | <span data-ttu-id="9dc81-115">Апрель 2015 г.</span><span class="sxs-lookup"><span data-stu-id="9dc81-115">April, 2015</span></span>                                        |

## <a name="abstract"></a><span data-ttu-id="9dc81-116">Аннотация</span><span class="sxs-lookup"><span data-stu-id="9dc81-116">Abstract</span></span>

<span data-ttu-id="9dc81-117">В этом документе приводятся официальные рекомендации для специалистов, планирующих внедрить опрашивающий сервер настройки требуемого состояния Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dc81-117">This document is designed to provide official guidance for anyone planning for a Windows PowerShell Desired State Configuration pull server implementation.</span></span> <span data-ttu-id="9dc81-118">Опрашивающий сервер представляет собой простую службу, которая должна развертываться за минуты.</span><span class="sxs-lookup"><span data-stu-id="9dc81-118">A pull server is a simple service that should take only minutes to deploy.</span></span> <span data-ttu-id="9dc81-119">Несмотря на то, что в этом документе и представлены технические практические инструкции по развертыванию, он ценен прежде всего тем, что является своего рода справочником с рекомендациями и советами относительно важных моментов, которые необходимо принимать во внимание перед развертыванием.</span><span class="sxs-lookup"><span data-stu-id="9dc81-119">Although this document will offer technical how-to guidance that can be used in a deployment, the value of this document is as a reference for best practices and what to think about before deploying.</span></span> <span data-ttu-id="9dc81-120">Читатели должны иметь общее представление о DSC и понимать термины, используемые для описания компонентов, входящих в развертывание DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-120">Readers should have basic familiarity with DSC, and the terms used to describe the components that are included in a DSC deployment.</span></span> <span data-ttu-id="9dc81-121">Дополнительные сведения см. в статье [Windows PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview) (Общие сведения о службе настройки требуемого состояния Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="9dc81-121">For more information, see the [Windows PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview) topic.</span></span> <span data-ttu-id="9dc81-122">Поскольку предполагается, что темп развития DSC соответствует скорости совершенствования облачных служб, можно ожидать, что базовая технология, включая опрашивающий сервер, также будет эволюционировать и давать новые возможности.</span><span class="sxs-lookup"><span data-stu-id="9dc81-122">As DSC is expected to evolve at cloud cadence, the underlying technology including pull server is also expected to evolve and to introduce new capabilities.</span></span> <span data-ttu-id="9dc81-123">В приложении к этому документу содержится таблица версий со ссылками на предыдущие выпуски и будущие решения для стимулирования разработки проектов с заделом на будущее.</span><span class="sxs-lookup"><span data-stu-id="9dc81-123">This document includes a version table in the appendix that provides references to previous releases and references to future looking solutions to encourage forward-looking designs.</span></span>

<span data-ttu-id="9dc81-124">Этот документ состоит из двух основных разделов:</span><span class="sxs-lookup"><span data-stu-id="9dc81-124">The two major sections of this document:</span></span>

- <span data-ttu-id="9dc81-125">Планирование настройки</span><span class="sxs-lookup"><span data-stu-id="9dc81-125">Configuration Planning</span></span>
- <span data-ttu-id="9dc81-126">Руководство по установке</span><span class="sxs-lookup"><span data-stu-id="9dc81-126">Installation Guide</span></span>

### <a name="versions-of-the-windows-management-framework"></a><span data-ttu-id="9dc81-127">Версии Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="9dc81-127">Versions of the Windows Management Framework</span></span>

<span data-ttu-id="9dc81-128">Информация в этом документе рассчитана на Windows Management Framework 5.0.</span><span class="sxs-lookup"><span data-stu-id="9dc81-128">The information in this document is intended to apply to Windows Management Framework 5.0.</span></span> <span data-ttu-id="9dc81-129">И хотя для развертывания и эксплуатации опрашивающего сервера WMF 5.0 и не требуется, акцент в этом документе сделан именно на версии 5.0.</span><span class="sxs-lookup"><span data-stu-id="9dc81-129">While WMF 5.0 is not required for deploying and operating a pull server, version 5.0 is the focus of this document.</span></span>

### <a name="windows-powershell-desired-state-configuration"></a><span data-ttu-id="9dc81-130">Настройка необходимого состояния Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dc81-130">Windows PowerShell Desired State Configuration</span></span>

<span data-ttu-id="9dc81-131">Настройка требуемого состояния (DSC) — это платформа управления для развертывания данных конфигурации и управления ими при помощи отраслевого синтаксиса Managed Object Format (MOF) для описания модели Common Information Model (CIM).</span><span class="sxs-lookup"><span data-stu-id="9dc81-131">Desired State Configuration (DSC) is a management platform that enables deploying and managing configuration data by using an industry syntax named the Managed Object Format (MOF) to describe the Common Information Model (CIM).</span></span> <span data-ttu-id="9dc81-132">Для дальнейшей разработки этих стандартов на платформах, включая Linux и операционные системы для сетевого оборудования, существует проект с открытым исходным кодом — открытая инфраструктура управления (Open Management Infrastructure, OMI).</span><span class="sxs-lookup"><span data-stu-id="9dc81-132">An open source project, Open Management Infrastructure (OMI), exists to further development of these standards across platforms including Linux and network hardware operating systems.</span></span> <span data-ttu-id="9dc81-133">Дополнительные сведения см. на [странице DMTF со спецификациями MOF](https://www.dmtf.org/standards/cim) и в [документах по OMI](https://collaboration.opengroup.org/omi/documents.php).</span><span class="sxs-lookup"><span data-stu-id="9dc81-133">For more information, see the [DMTF page linking to MOF specifications](https://www.dmtf.org/standards/cim), and [OMI Documents and Source](https://collaboration.opengroup.org/omi/documents.php).</span></span>

<span data-ttu-id="9dc81-134">Windows PowerShell предоставляет набор расширений языка для настройки требуемого состояния, который можно использовать для создания декларативных конфигураций и управления ими.</span><span class="sxs-lookup"><span data-stu-id="9dc81-134">Windows PowerShell provides a set of language extensions for Desired State Configuration that you can use to create and manage declarative configurations.</span></span>

### <a name="pull-server-role"></a><span data-ttu-id="9dc81-135">Роль опрашивающего сервера</span><span class="sxs-lookup"><span data-stu-id="9dc81-135">Pull server role</span></span>

<span data-ttu-id="9dc81-136">Опрашивающий сервер является централизованной службой для хранения конфигураций, которые будут доступны для целевых узлов.</span><span class="sxs-lookup"><span data-stu-id="9dc81-136">A pull server provides a centralized service to store configurations that will be accessible to target nodes.</span></span>

<span data-ttu-id="9dc81-137">Роль опрашивающего сервера может быть развернута как экземпляр веб-сервера или общая папка SMB.</span><span class="sxs-lookup"><span data-stu-id="9dc81-137">The pull server role can be deployed as either a Web Server instance or an SMB file share.</span></span> <span data-ttu-id="9dc81-138">Веб-сервер использует интерфейс OData и при необходимости может включать в себя возможности, позволяющие целевым узлам подтверждать успешное применение конфигураций или сообщать о неудаче.</span><span class="sxs-lookup"><span data-stu-id="9dc81-138">The web server capability includes an OData interface and can optionally include capabilities for target nodes to report back confirmation of success or failure as configurations are applied.</span></span> <span data-ttu-id="9dc81-139">Это полезно в средах с большим числом целевых узлов.</span><span class="sxs-lookup"><span data-stu-id="9dc81-139">This functionality is useful in environments where there are a large number of target nodes.</span></span> <span data-ttu-id="9dc81-140">После настройки целевого узла (также называемого клиентом) на указание на опрашивающий сервер происходит скачивание и применение последних данных конфигурации и всех необходимых скриптов.</span><span class="sxs-lookup"><span data-stu-id="9dc81-140">After configuring a target node (also referred to as a client) to point to the pull server the latest configuration data and any required scripts are downloaded and applied.</span></span> <span data-ttu-id="9dc81-141">Этот процесс может быть реализован как однократное развертывание или как повторно выполняющееся задание, что делает опрашивающий сервер важным активом для управления изменениями на должном уровне.</span><span class="sxs-lookup"><span data-stu-id="9dc81-141">This can happen as a one-time deployment or as a re-occurring job which also makes the pull server an important asset for managing change at scale.</span></span> <span data-ttu-id="9dc81-142">Дополнительные сведения см. в статьях [Настройка опрашивающего веб-сервера DSC](pullserver.md) и [Push and Pull Configuration Modes](pullserver.md) (Режимы конфигурации Push и Pull).</span><span class="sxs-lookup"><span data-stu-id="9dc81-142">For more information, see [Windows PowerShell Desired State Configuration Pull Servers](pullserver.md) and [Push and Pull Configuration Modes](pullserver.md).</span></span>

## <a name="configuration-planning"></a><span data-ttu-id="9dc81-143">Планирование настройки</span><span class="sxs-lookup"><span data-stu-id="9dc81-143">Configuration planning</span></span>

<span data-ttu-id="9dc81-144">В рамках любого развертывания программного обеспечения в организации существует информация, которую можно собрать заранее, чтобы спланировать нужную архитектуру и подготовиться к этапам, необходимым для выполнения развертывания.</span><span class="sxs-lookup"><span data-stu-id="9dc81-144">For any enterprise software deployment there is information that can be collected in advance to help plan for the correct architecture and to be prepared for the steps required to complete the deployment.</span></span> <span data-ttu-id="9dc81-145">В следующих разделах приводится информация о подготовке и подключениях, которые, скорее всего, потребуется реализовать заблаговременно.</span><span class="sxs-lookup"><span data-stu-id="9dc81-145">The following sections provide information regarding how to prepare and the organizational connections that will likely need to happen in advance.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="9dc81-146">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="9dc81-146">Software requirements</span></span>

<span data-ttu-id="9dc81-147">Для развертывания опрашивающего сервера требуется служба DSC сервера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9dc81-147">Deployment of a pull server requires the DSC Service feature of Windows Server.</span></span> <span data-ttu-id="9dc81-148">Этот компонент появился в Windows Server 2012 и обновлялся в рамках текущих выпусков Windows Management Framework (WMF).</span><span class="sxs-lookup"><span data-stu-id="9dc81-148">This feature was introduced in Windows Server 2012, and has been updated through ongoing releases of Windows Management Framework (WMF).</span></span>

### <a name="software-downloads"></a><span data-ttu-id="9dc81-149">Файлы программного обеспечения для скачивания</span><span class="sxs-lookup"><span data-stu-id="9dc81-149">Software downloads</span></span>

<span data-ttu-id="9dc81-150">Помимо установки новейшего содержимого из Центра обновления Windows, есть два скачиваемых компонента, рекомендуемых для развертывания опрашиваемого сервера DSC: последняя версия Windows Management Framework и модуль DSC для автоматизированной подготовки опрашиваемого сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc81-150">In addition to installing the latest content from Windows Update, there are two downloads considered best practice to deploy a DSC pull server: The latest version of Windows Management Framework, and a DSC module to automate pull server provisioning.</span></span>

### <a name="wmf"></a><span data-ttu-id="9dc81-151">WMF</span><span class="sxs-lookup"><span data-stu-id="9dc81-151">WMF</span></span>

<span data-ttu-id="9dc81-152">В состав Windows Server 2012 R2 входит компонент, который называется службой DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-152">Windows Server 2012 R2 includes a feature named the DSC Service.</span></span> <span data-ttu-id="9dc81-153">Служба DSC обеспечивает функциональность опрашивающего сервера, включая предоставление двоичных файлов, которые поддерживают конечную точку OData.</span><span class="sxs-lookup"><span data-stu-id="9dc81-153">The DSC Service feature provides the pull server functionality, including the binaries that support the OData endpoint.</span></span> <span data-ttu-id="9dc81-154">WMF является частью Windows Server и регулярно обновляется между выпусками Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9dc81-154">WMF is included in Windows Server and is updated on an agile cadence between Windows Server releases.</span></span>
<span data-ttu-id="9dc81-155">[Новые версии WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=54616) могут содержать обновления для службы DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-155">[New versions of WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=54616) can include updates to the DSC Service feature.</span></span> <span data-ttu-id="9dc81-156">Поэтому рекомендуется скачать последний выпуск WMF и ознакомиться с заметками о нем, чтобы узнать, есть ли обновление для службы DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-156">For this reason, it is a best practice to download the latest release of WMF and to review the release notes to determine if the release includes an update to the DSC service feature.</span></span> <span data-ttu-id="9dc81-157">Кроме того, в заметках о выпуске следует просмотреть раздел, где указано состояние обновления или сценария (стабильный выпуск или экспериментальный).</span><span class="sxs-lookup"><span data-stu-id="9dc81-157">You should also review the section of the release notes that indicates whether the design status for an update or scenario is listed as stable or experimental.</span></span> <span data-ttu-id="9dc81-158">Чтобы реализовать гибкий цикл выпуска, отдельные компоненты могут быть объявлены стабильными, что говорит об их готовности к использованию в рабочей среде даже в том случае, если выпущена лишь предварительная версия WMF.</span><span class="sxs-lookup"><span data-stu-id="9dc81-158">To allow for an agile release cycle, individual features can be declared stable, which indicates the feature is ready to be used in a production environment even while WMF is released in preview.</span></span> <span data-ttu-id="9dc81-159">Другие компоненты, которые исторически обновлялись в выпусках WMF (подробности см. в заметках о выпуске WMF):</span><span class="sxs-lookup"><span data-stu-id="9dc81-159">Other features that have historically been updated by WMF releases (see the WMF Release Notes for further detail):</span></span>

- <span data-ttu-id="9dc81-160">Windows PowerShell, интегрированная среда скриптов Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="9dc81-160">Windows PowerShell Windows PowerShell Integrated Scripting</span></span>
- <span data-ttu-id="9dc81-161">Веб-службы Windows PowerShell (расширение IIS OData для управления).</span><span class="sxs-lookup"><span data-stu-id="9dc81-161">Environment (ISE) Windows PowerShell Web Services (Management OData</span></span>
- <span data-ttu-id="9dc81-162">Настройка требуемого состояния Windows PowerShell (DSC).</span><span class="sxs-lookup"><span data-stu-id="9dc81-162">IIS Extension)  Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="9dc81-163">Удаленное управление Windows (WinRM), инструментарий управления Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="9dc81-163">Windows Remote Management (WinRM) Windows Management Instrumentation (WMI)</span></span>

### <a name="dsc-resource"></a><span data-ttu-id="9dc81-164">Ресурс DSC</span><span class="sxs-lookup"><span data-stu-id="9dc81-164">DSC resource</span></span>

<span data-ttu-id="9dc81-165">Развертывание опрашивающего сервера можно упростить, подготовив службу с использованием скрипта настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-165">A pull server deployment can be simplified by provisioning the service using a DSC configuration script.</span></span> <span data-ttu-id="9dc81-166">В этот документ включены скрипты настройки, которые можно использовать для развертывания узла сервера, готового к внедрению в рабочую среду.</span><span class="sxs-lookup"><span data-stu-id="9dc81-166">This document includes configuration scripts that can be used to deploy a production ready server node.</span></span> <span data-ttu-id="9dc81-167">Для использования скриптов настройки требуется модуль DSC, не входящий в состав Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9dc81-167">To use the configuration scripts, a DSC module is required that is not included in Windows Server.</span></span> <span data-ttu-id="9dc81-168">Название модуля — **xPSDesiredStateConfiguration**; модуль содержит ресурс DSC **xDscWebService**.</span><span class="sxs-lookup"><span data-stu-id="9dc81-168">The required module name is **xPSDesiredStateConfiguration**, which includes the DSC resource **xDscWebService**.</span></span> <span data-ttu-id="9dc81-169">Модуль xPSDesiredStateConfiguration можно скачать [здесь](https://gallery.technet.microsoft.com/xPSDesiredStateConfiguratio-417dc71d).</span><span class="sxs-lookup"><span data-stu-id="9dc81-169">The xPSDesiredStateConfiguration module can be downloaded [here](https://gallery.technet.microsoft.com/xPSDesiredStateConfiguratio-417dc71d).</span></span>

<span data-ttu-id="9dc81-170">Используйте командлет `Install-Module` из модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="9dc81-170">Use the `Install-Module` cmdlet from the **PowerShellGet** module.</span></span>

```powershell
Install-Module xPSDesiredStateConfiguration
```

<span data-ttu-id="9dc81-171">Модуль **PowerShellGet** скачает модуль в следующую папку:</span><span class="sxs-lookup"><span data-stu-id="9dc81-171">The **PowerShellGet** module will download the module to:</span></span>

`C:\Program Files\Windows PowerShell\Modules`

<span data-ttu-id="9dc81-172">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-172">Planning task</span></span>

- <span data-ttu-id="9dc81-173">Есть ли у вас доступ к установочным файлам Windows Server 2012 R2?</span><span class="sxs-lookup"><span data-stu-id="9dc81-173">Do you have access to the installation files for Windows Server 2012 R2?</span></span>
- <span data-ttu-id="9dc81-174">Будет ли у среды развертывания доступ к Интернету для скачивания WMF и модуля из коллекции в сети?</span><span class="sxs-lookup"><span data-stu-id="9dc81-174">Will the deployment environment have Internet access to download WMF and the module from the online gallery?</span></span>
- <span data-ttu-id="9dc81-175">Каким образом будут установлены последние обновления для системы безопасности после установки операционной системы?</span><span class="sxs-lookup"><span data-stu-id="9dc81-175">How will you install the latest security updates after installing the operating system?</span></span>
- <span data-ttu-id="9dc81-176">Будет ли у среды доступ к Интернету для получения обновлений или же в ней будет размещен локальный сервер с Windows Server Update Services (WSUS)?</span><span class="sxs-lookup"><span data-stu-id="9dc81-176">Will the environment have Internet access to obtain updates, or will it have a local Windows Server Update Services (WSUS) server?</span></span>
- <span data-ttu-id="9dc81-177">Есть ли у вас доступ к установочным файлам Windows Server, уже содержащим обновления, добавленные посредством вставки?</span><span class="sxs-lookup"><span data-stu-id="9dc81-177">Do you have access to Windows Server installation files that already include updates through offline injection?</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="9dc81-178">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="9dc81-178">Hardware requirements</span></span>

<span data-ttu-id="9dc81-179">Развертывания опрашивающих серверов поддерживаются как на физических, так и виртуальных серверах.</span><span class="sxs-lookup"><span data-stu-id="9dc81-179">Pull server deployments are supported on both physical and virtual servers.</span></span> <span data-ttu-id="9dc81-180">Требования к размеру для опрашивающего сервера соответствуют требованиям Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="9dc81-180">The sizing requirements for pull server align with the requirements for Windows Server 2012 R2.</span></span>

- <span data-ttu-id="9dc81-181">Процессор: 64-разрядный процессор с тактовой частотой 1,4 ГГц</span><span class="sxs-lookup"><span data-stu-id="9dc81-181">CPU: 1.4 GHz 64-bit processor</span></span>
- <span data-ttu-id="9dc81-182">Память: 512 МБ</span><span class="sxs-lookup"><span data-stu-id="9dc81-182">Memory: 512 MB</span></span>
- <span data-ttu-id="9dc81-183">Место на диске: 32 ГБ</span><span class="sxs-lookup"><span data-stu-id="9dc81-183">Disk Space: 32 GB</span></span>
- <span data-ttu-id="9dc81-184">Сеть. адаптер Gigabit Ethernet.</span><span class="sxs-lookup"><span data-stu-id="9dc81-184">Network: Gigabit Ethernet Adapter</span></span>

<span data-ttu-id="9dc81-185">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-185">Planning task</span></span>

- <span data-ttu-id="9dc81-186">Развертывание будет выполняться на физическом оборудовании или платформе виртуализации?</span><span class="sxs-lookup"><span data-stu-id="9dc81-186">Will you deploy on physical hardware or on a virtualization platform?</span></span>
- <span data-ttu-id="9dc81-187">В чем заключается процесс запроса нового сервера для целевой среды?</span><span class="sxs-lookup"><span data-stu-id="9dc81-187">What is the process to request a new server for your target environment?</span></span>
- <span data-ttu-id="9dc81-188">Каково среднее время получения доступа к серверу?</span><span class="sxs-lookup"><span data-stu-id="9dc81-188">What is the average turnaround time for a server to become available?</span></span>
- <span data-ttu-id="9dc81-189">Сервер какого размера будет запрошен?</span><span class="sxs-lookup"><span data-stu-id="9dc81-189">What size server will you request?</span></span>

### <a name="accounts"></a><span data-ttu-id="9dc81-190">Учетные записи</span><span class="sxs-lookup"><span data-stu-id="9dc81-190">Accounts</span></span>

<span data-ttu-id="9dc81-191">Требования, связанные с учетными записями служб, для развертывания экземпляра опрашивающего сервера отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="9dc81-191">There are no service account requirements to deploy a pull server instance.</span></span> <span data-ttu-id="9dc81-192">Однако в некоторых случаях веб-сайт может работать в контексте учетной записи локального пользователя.</span><span class="sxs-lookup"><span data-stu-id="9dc81-192">However, there are scenarios where the website could run in the context of a local user account.</span></span> <span data-ttu-id="9dc81-193">Например, иногда необходимо получить доступ к общей папке хранилища с содержимым веб-сайта, а сервер Windows Server или устройство, на котором размещена общая папка хранилища, не присоединены к домену.</span><span class="sxs-lookup"><span data-stu-id="9dc81-193">For example, if there is a need to access a storage share for website content and either the Windows Server or the device hosting the storage share are not domain joined.</span></span>

### <a name="dns-records"></a><span data-ttu-id="9dc81-194">Записи DNS</span><span class="sxs-lookup"><span data-stu-id="9dc81-194">DNS records</span></span>

<span data-ttu-id="9dc81-195">При настройке клиентов для работы в среде опрашивающего сервера вам потребуется название сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc81-195">You will need a server name to use when configuring clients to work with a pull server environment.</span></span>
<span data-ttu-id="9dc81-196">В тестовой среде обычно используется имя узла сервера, а если разрешение имен DNS недоступно, можно использовать IP-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc81-196">In test environments, typically the server hostname is used, or the IP address for the server can be used if DNS name resolution is not available.</span></span> <span data-ttu-id="9dc81-197">В рабочих средах или в лабораторной среде, предназначенной для представления рабочего развертывания, рекомендуется создать запись DNS CNAME.</span><span class="sxs-lookup"><span data-stu-id="9dc81-197">In production environments or in a lab environment that is intended to represent a production deployment, the best practice is to create a DNS CNAME record.</span></span>

<span data-ttu-id="9dc81-198">Запись DNS CNAME позволяет сформировать псевдоним для ссылки на запись узла (A).</span><span class="sxs-lookup"><span data-stu-id="9dc81-198">A DNS CNAME allows you to create an alias to refer to your host (A) record.</span></span> <span data-ttu-id="9dc81-199">Дополнительная запись имени предназначена для повышения гибкости, если в будущем потребуется вносить изменения.</span><span class="sxs-lookup"><span data-stu-id="9dc81-199">The intent of the additional name record is to increase flexibility should a change be required in the future.</span></span> <span data-ttu-id="9dc81-200">Запись CNAME помогает изолировать конфигурацию клиента, чтобы в случае внесения изменений в серверную среду (например, замена опрашивающего сервера или добавление дополнительных опрашивающих серверов), не потребовалось изменять конфигурацию клиента соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="9dc81-200">A CNAME can help to isolate the client configuration so that changes to the server environment, such as replacing a pull server or adding additional pull servers, will not require a corresponding change to the client configuration.</span></span>

<span data-ttu-id="9dc81-201">При выборе названия для записи DNS следует учитывать архитектуру решения.</span><span class="sxs-lookup"><span data-stu-id="9dc81-201">When choosing a name for the DNS record, keep the solution architecture in mind.</span></span>
<span data-ttu-id="9dc81-202">Если используется балансировка нагрузки, название сертификата, применяемого для защиты трафика по протоколу HTTPS, должно совпадать с названием записи DNS.</span><span class="sxs-lookup"><span data-stu-id="9dc81-202">If using load balancing, the certificate used to secure traffic over HTTPS will need to share the same name as the DNS record.</span></span>

|       <span data-ttu-id="9dc81-203">Сценарий</span><span class="sxs-lookup"><span data-stu-id="9dc81-203">Scenario</span></span>        |                                                                                         <span data-ttu-id="9dc81-204">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9dc81-204">Best Practice</span></span>
|:--------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
|<span data-ttu-id="9dc81-205">Тестовая среда</span><span class="sxs-lookup"><span data-stu-id="9dc81-205">Test Environment</span></span>       | <span data-ttu-id="9dc81-206">По возможности воспроизведите запланированную рабочую среду.</span><span class="sxs-lookup"><span data-stu-id="9dc81-206">Reproduce the planned production environment, if possible.</span></span> <span data-ttu-id="9dc81-207">Для простых конфигураций подойдет имя узла сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc81-207">A server hostname is suitable for simple configurations.</span></span> <span data-ttu-id="9dc81-208">Если служба DNS недоступна, вместо имени узла можно использовать IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="9dc81-208">If DNS is not available, an IP address may be used in lieu of a hostname.</span></span>
|<span data-ttu-id="9dc81-209">Развертывание одного узла</span><span class="sxs-lookup"><span data-stu-id="9dc81-209">Single Node Deployment</span></span> | <span data-ttu-id="9dc81-210">Создайте запись DNS CNAME, которая указывает на имя узла сервера.</span><span class="sxs-lookup"><span data-stu-id="9dc81-210">Create a DNS CNAME record that points to the server hostname.</span></span>

<span data-ttu-id="9dc81-211">Дополнительные сведения см. в статье [Configuring DNS Round Robin in Windows Server](/previous-versions/windows/it-pro/windows-server-2003/cc787484(v=ws.10)) (Настройка циклического перебора DNS в Windows Server).</span><span class="sxs-lookup"><span data-stu-id="9dc81-211">For more information, see [Configuring DNS Round Robin in Windows Server](/previous-versions/windows/it-pro/windows-server-2003/cc787484(v=ws.10)).</span></span>

<span data-ttu-id="9dc81-212">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-212">Planning task</span></span>

- <span data-ttu-id="9dc81-213">Вы знаете, к кому обращаться по вопросам создания и изменения записей DNS?</span><span class="sxs-lookup"><span data-stu-id="9dc81-213">Do you know who to contact to have DNS records created and changed?</span></span>
- <span data-ttu-id="9dc81-214">Каково среднее время обработки запроса, связанного с записью DNS?</span><span class="sxs-lookup"><span data-stu-id="9dc81-214">What is the average turnaround for a request for a DNS record?</span></span>
- <span data-ttu-id="9dc81-215">Вам требуется запрашивать статические записи имени узла (A) для серверов?</span><span class="sxs-lookup"><span data-stu-id="9dc81-215">Do you need to request static Hostname (A) records for servers?</span></span>
- <span data-ttu-id="9dc81-216">Что вы будете запрашивать в качестве CNAME?</span><span class="sxs-lookup"><span data-stu-id="9dc81-216">What will you request as a CNAME?</span></span>
- <span data-ttu-id="9dc81-217">Какой тип решения по балансировке нагрузки вы будете использовать в случае необходимости?</span><span class="sxs-lookup"><span data-stu-id="9dc81-217">If needed, what type of Load Balancing solution will you utilize?</span></span> <span data-ttu-id="9dc81-218">(Дополнительные сведения см. в разделе о балансировке нагрузки.)</span><span class="sxs-lookup"><span data-stu-id="9dc81-218">(see section titled Load Balancing for details)</span></span>

### <a name="public-key-infrastructure"></a><span data-ttu-id="9dc81-219">Инфраструктура открытых ключей</span><span class="sxs-lookup"><span data-stu-id="9dc81-219">Public Key Infrastructure</span></span>

<span data-ttu-id="9dc81-220">Большинству современных организаций требуется проверка и шифрование передаваемого сетевого трафика и, в частности, трафика, содержащего конфиденциальные данные о конфигурации серверов.</span><span class="sxs-lookup"><span data-stu-id="9dc81-220">Most organizations today require that network traffic, especially traffic that includes such sensitive data as how servers are configured, must be validated and/or encrypted during transit.</span></span>
<span data-ttu-id="9dc81-221">Несмотря на то, что опрашивающий сервер можно развернуть с использованием протокола HTTP, что облегчает обработку запросов от клиентов (так как используется открытый текст), рекомендуется защитить трафик при помощи протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9dc81-221">While it is possible to deploy a pull server using HTTP which facilitates client requests in clear text, it is a best practice to secure traffic using HTTPS.</span></span> <span data-ttu-id="9dc81-222">Службу можно настроить на использование HTTPS, применив набор параметров в ресурсе DSC **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9dc81-222">The service can be configured to use HTTPS using a set of parameters in the DSC resource **xPSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="9dc81-223">Требования, касающиеся сертификатов, для защиты трафика HTTPS опрашивающего сервера аналогичны требованиям, применимым к защите любого другого веб-сайта с HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9dc81-223">The certificate requirements to secure HTTPS traffic for pull server are not different than securing any other HTTPS web site.</span></span> <span data-ttu-id="9dc81-224">Шаблон **веб-сервера** в службах сертификации Windows Server удовлетворяет необходимым условиям.</span><span class="sxs-lookup"><span data-stu-id="9dc81-224">The **Web Server** template in a Windows Server Certificate Services satisfies the required capabilities.</span></span>

<span data-ttu-id="9dc81-225">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-225">Planning task</span></span>

- <span data-ttu-id="9dc81-226">К кому потребуется обратиться для получения сертификата (если запросы на сертификаты не обрабатываются автоматически)?</span><span class="sxs-lookup"><span data-stu-id="9dc81-226">If certificate requests are not automated, who will you need to contact to requests a certificate?</span></span>
- <span data-ttu-id="9dc81-227">Каково среднее время обработки запроса?</span><span class="sxs-lookup"><span data-stu-id="9dc81-227">What is the average turnaround for the request?</span></span>
- <span data-ttu-id="9dc81-228">Каким образом вам будет передан файл сертификата?</span><span class="sxs-lookup"><span data-stu-id="9dc81-228">How will the certificate file be transferred to you?</span></span>
- <span data-ttu-id="9dc81-229">Каким образом вам будет передан закрытый ключ сертификата?</span><span class="sxs-lookup"><span data-stu-id="9dc81-229">How will the certificate private key be transferred to you?</span></span>
- <span data-ttu-id="9dc81-230">Каков срок действия по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="9dc81-230">How long is the default expiration time?</span></span>
- <span data-ttu-id="9dc81-231">Вы выбрали имя DNS для среды опрашивающего сервера, которое можно использовать в названии сертификата?</span><span class="sxs-lookup"><span data-stu-id="9dc81-231">Have you settled on a DNS name for the pull server environment, that you can use for the certificate name?</span></span>

### <a name="choosing-an-architecture"></a><span data-ttu-id="9dc81-232">Выбор архитектуры</span><span class="sxs-lookup"><span data-stu-id="9dc81-232">Choosing an architecture</span></span>

<span data-ttu-id="9dc81-233">Опрашивающий сервер можно развернуть при помощи веб-службы, размещенной в службах IIS, или общей папки SMB.</span><span class="sxs-lookup"><span data-stu-id="9dc81-233">A pull server can be deployed using either a web service hosted on IIS, or an SMB file share.</span></span> <span data-ttu-id="9dc81-234">В большинстве случаев вариант с использованием веб-службы обеспечит большую гибкость.</span><span class="sxs-lookup"><span data-stu-id="9dc81-234">In most situations, the web service option will provide greater flexibility.</span></span> <span data-ttu-id="9dc81-235">Как правило, трафик HTTPS проходит через границы сети, тогда как трафик SMB часто отфильтровывается или блокируется между сетями.</span><span class="sxs-lookup"><span data-stu-id="9dc81-235">It is not uncommon for HTTPS traffic to traverse network boundaries, whereas SMB traffic is often filtered or blocked between networks.</span></span> <span data-ttu-id="9dc81-236">Веб-служба предусматривает возможность включения Conformance Server или диспетчера веб-отчетов (Web Reporting Manager) (оба компонента будут рассматриваться в будущей версии этого документа), которые предоставляют для клиентов механизм сообщения о состоянии на сервер в целях централизованного контроля.</span><span class="sxs-lookup"><span data-stu-id="9dc81-236">The web service also offers the option to include a Conformance Server or Web Reporting Manager (both topics to be addressed in a future version of this document) that provide a mechanism for clients to report status back to a server for centralized visibility.</span></span> <span data-ttu-id="9dc81-237">SMB подходит для использования в средах, где политика запрещает эксплуатацию веб-сервера, и в других ситуациях, когда применение роли веб-сервера является нежелательным.</span><span class="sxs-lookup"><span data-stu-id="9dc81-237">SMB provides an option for environments where policy dictates that a web server should not be utilized, and for other environmental requirements that make a web server role undesirable.</span></span> <span data-ttu-id="9dc81-238">Вне зависимости от выбранного варианта не забудьте оценить требования, касающиеся подписывания и шифрования трафика.</span><span class="sxs-lookup"><span data-stu-id="9dc81-238">In either case, remember to evaluate the requirements for signing and encrypting traffic.</span></span> <span data-ttu-id="9dc81-239">Стоит принять во внимание такие моменты, как передача трафика HTTPS, подписывание SMB и политики IPSEC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-239">HTTPS, SMB signing, and IPSEC policies are all options worth considering.</span></span>

#### <a name="load-balancing"></a><span data-ttu-id="9dc81-240">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="9dc81-240">Load balancing</span></span>

<span data-ttu-id="9dc81-241">Клиенты, взаимодействующие с веб-службой, направляют запрос на получение данных, возвращаемых в одном ответе.</span><span class="sxs-lookup"><span data-stu-id="9dc81-241">Clients interacting with the web service make a request for information that is returned in a single response.</span></span> <span data-ttu-id="9dc81-242">Последующие запросы не нужны, поэтому платформе балансировки нагрузки не требуется обеспечивать постоянную поддержку сеансов на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="9dc81-242">No sequential requests are required, so it is not necessary for the load balancing platform to ensure sessions are maintained on a single server at any point in time.</span></span>

<span data-ttu-id="9dc81-243">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-243">Planning task</span></span>

- <span data-ttu-id="9dc81-244">Какое решение будет использоваться для балансировки нагрузки трафика между серверами?</span><span class="sxs-lookup"><span data-stu-id="9dc81-244">What solution will be used for load balancing traffic across servers?</span></span>
- <span data-ttu-id="9dc81-245">Кто выполнит запрос на добавление новой конфигурации на устройство в случае использования аппаратной подсистемы балансировки нагрузки?</span><span class="sxs-lookup"><span data-stu-id="9dc81-245">If using a hardware load balancer, who will take a request to add a new configuration to the device?</span></span>
- <span data-ttu-id="9dc81-246">Каково среднее время обработки запроса на настройку новой веб-службы с балансировкой нагрузки?</span><span class="sxs-lookup"><span data-stu-id="9dc81-246">What is the average turnaround for a request to configure a new load balanced web service?</span></span>
- <span data-ttu-id="9dc81-247">Какие данные будут необходимы для запроса?</span><span class="sxs-lookup"><span data-stu-id="9dc81-247">What information will be required for the request?</span></span>
- <span data-ttu-id="9dc81-248">Запрашивать дополнительный IP-адрес будете вы или рабочая группа, ответственная за балансировку нагрузки?</span><span class="sxs-lookup"><span data-stu-id="9dc81-248">Will you need to request an additional IP or will the team responsible for load balancing handle that?</span></span>
- <span data-ttu-id="9dc81-249">Есть ли у вас необходимые записи DNS? Потребуются ли они рабочей группе, отвечающей за настройку решения по балансировке нагрузки?</span><span class="sxs-lookup"><span data-stu-id="9dc81-249">Do you have the DNS records needed, and will this be required by the team responsible for configuring the load balancing solution?</span></span>
- <span data-ttu-id="9dc81-250">Нужно ли, чтобы в решении по балансировке нагрузки обработку PKI выполняло устройство? Или балансировка нагрузки трафика HTTPS может осуществляться до тех пор, пока отсутствуют требования, связанные сеансами?</span><span class="sxs-lookup"><span data-stu-id="9dc81-250">Does the load balancing solution require that PKI be handled by the device or can it load balance HTTPS traffic as long as there are no session requirements?</span></span>

### <a name="staging-configurations-and-modules-on-the-pull-server"></a><span data-ttu-id="9dc81-251">Промежуточные конфигурации и модули на опрашивающем сервере</span><span class="sxs-lookup"><span data-stu-id="9dc81-251">Staging configurations and modules on the pull server</span></span>

<span data-ttu-id="9dc81-252">При планировании конфигурации необходимо подумать о том, какие модули DSC и конфигурации будут размещены на опрашивающем сервере.</span><span class="sxs-lookup"><span data-stu-id="9dc81-252">As part of configuration planning, you will need to think about which DSC modules and configurations will be hosted by the pull server.</span></span> <span data-ttu-id="9dc81-253">Кроме того, важно иметь базовые знания о принципах развертывания содержимого на опрашивающем сервере и подготовки к этому процессу.</span><span class="sxs-lookup"><span data-stu-id="9dc81-253">For the purpose of configuration planning it is important to have a basic understanding of how to prepare and deploy content to a pull server.</span></span>

<span data-ttu-id="9dc81-254">В будущем этот раздел будет расширен и включен в руководство по эксплуатации опрашивающего сервера DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-254">In the future, this section will be expanded and included in an Operations Guide for DSC Pull Server.</span></span> <span data-ttu-id="9dc81-255">В руководстве будет рассматриваться рутинный процесс управления модулями и конфигурациями с применением автоматизации.</span><span class="sxs-lookup"><span data-stu-id="9dc81-255">The guide will discuss the day to day process for managing modules and configurations over time with automation.</span></span>

#### <a name="dsc-modules"></a><span data-ttu-id="9dc81-256">Модули DSC</span><span class="sxs-lookup"><span data-stu-id="9dc81-256">DSC modules</span></span>

<span data-ttu-id="9dc81-257">Клиентам, запрашивающим конфигурацию, потребуются некоторые модули DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-257">Clients that request a configuration will need the required DSC modules.</span></span> <span data-ttu-id="9dc81-258">Функциональность опрашивающего сервера заключается в автоматизации распространения модулей DSC на клиенты по запросу.</span><span class="sxs-lookup"><span data-stu-id="9dc81-258">A functionality of the pull server is to automate distribution on demand of DSC modules to clients.</span></span> <span data-ttu-id="9dc81-259">При первом развертывании опрашивающего сервера (возможно, для проверки концепции или в тестовой среде) вы, скорее всего, будете зависеть от модулей DSC из общедоступных репозиториев, таких как коллекция PowerShell или репозитории PowerShell.org на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="9dc81-259">If you are deploying a pull server for the first time, perhaps as a lab or proof of concept, you are likely going to depend on DSC modules that are available from public repositories such as the PowerShell Gallery or the PowerShell.org GitHub repositories for DSC modules.</span></span>

<span data-ttu-id="9dc81-260">Важно помнить, что даже при использовании надежных сетевых источников, таких как коллекция PowerShell, любой модуль, скачиваемый из общедоступного репозитория, должен быть проверен специалистом с опытом работы с PowerShell и знаниями о среде, где будут использоваться модули, прежде чем они будут внедрены в рабочие условия.</span><span class="sxs-lookup"><span data-stu-id="9dc81-260">It is critical to remember that even for trusted online sources such as the PowerShell Gallery, any module that is downloaded from a public repository should be reviewed by someone with PowerShell experience and knowledge of the environment where the modules will be used prior to being used in production.</span></span> <span data-ttu-id="9dc81-261">При выполнении этой задачи рекомендуется проверить наличие в модуле дополнительных полезных данных, которые можно удалить, например документацию и скрипты-примеры.</span><span class="sxs-lookup"><span data-stu-id="9dc81-261">While completing this task it is a good time to check for any additional payload in the module that can be removed such as documentation and example scripts.</span></span> <span data-ttu-id="9dc81-262">Это позволит снизить долю полосы пропускания, используемую каждым клиентом при первом запросе, когда будет выполняться скачивание модулей с сервера на клиент по сети.</span><span class="sxs-lookup"><span data-stu-id="9dc81-262">This will reduce the network bandwidth per client in their first request, when modules will be downloaded over the network from server to client.</span></span>

<span data-ttu-id="9dc81-263">Каждый модуль должны быть упакован в определенном формате — это должен быть ZIP-файл с названием в формате "Название_модуля_Версия.zip", который содержит полезные данные модуля.</span><span class="sxs-lookup"><span data-stu-id="9dc81-263">Each module must be packaged in a specific format, a ZIP file named ModuleName_Version.zip that contains the module payload.</span></span> <span data-ttu-id="9dc81-264">После копирования файла на сервер необходимо создать файл контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="9dc81-264">After the file is copied to the server a checksum file must be created.</span></span>
<span data-ttu-id="9dc81-265">При подключении клиентов к серверу контрольная сумма используется для проверки неизменности содержимого модуля DSC с момента его публикации.</span><span class="sxs-lookup"><span data-stu-id="9dc81-265">When clients connect to the server, the checksum is used to verify the content of the DSC module has not changed since it was published.</span></span>

```powershell
New-DscChecksum -ConfigurationPath .\ -OutPath .\
```

<span data-ttu-id="9dc81-266">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-266">Planning task</span></span>

- <span data-ttu-id="9dc81-267">Какие ключевые ситуации следует проверить при планировании реализации тестовой или лабораторной среды?</span><span class="sxs-lookup"><span data-stu-id="9dc81-267">If you are planning a test or lab environment which scenarios are key to validate?</span></span>
- <span data-ttu-id="9dc81-268">Существуют ли общедоступные модули, которые содержат ресурсы, охватывающие все, что вам нужно, или вам потребуется создать собственные ресурсы?</span><span class="sxs-lookup"><span data-stu-id="9dc81-268">Are there publicly available modules that contain resources to cover everything you need or will you need to author your own resources?</span></span>
- <span data-ttu-id="9dc81-269">Будет ли у вашей среды доступ к Интернету для получения общедоступных модулей?</span><span class="sxs-lookup"><span data-stu-id="9dc81-269">Will your environment have Internet access to retrieve public modules?</span></span>
- <span data-ttu-id="9dc81-270">Кто будет отвечать за проверку модулей DSC?</span><span class="sxs-lookup"><span data-stu-id="9dc81-270">Who will be responsible for reviewing DSC modules?</span></span>
- <span data-ttu-id="9dc81-271">Если вы планируете производственную среду, что вы будете использовать в качестве локального репозитория для хранения модулей DSC?</span><span class="sxs-lookup"><span data-stu-id="9dc81-271">If you are planning a production environment what will you use as a local repository for storing DSC modules?</span></span>
- <span data-ttu-id="9dc81-272">Будет ли центральная рабочая группа принимать модули DSC от рабочих групп по разработке приложений?</span><span class="sxs-lookup"><span data-stu-id="9dc81-272">Will a central team accept DSC modules from application teams?</span></span> <span data-ttu-id="9dc81-273">В чем будет заключаться процесс?</span><span class="sxs-lookup"><span data-stu-id="9dc81-273">What will the process be?</span></span>
- <span data-ttu-id="9dc81-274">Будут ли автоматизированы процессы упаковки, копирования и создания контрольной суммы для модулей DSC, готовых к развертыванию на сервере в рабочей среде, из исходного репозитория?</span><span class="sxs-lookup"><span data-stu-id="9dc81-274">Will you automate packaging, copying, and creating a checksum for production-ready DSC modules to the server, from your source repo?</span></span>
- <span data-ttu-id="9dc81-275">Будет ли ваша рабочая группа отвечать за управление платформой автоматизации?</span><span class="sxs-lookup"><span data-stu-id="9dc81-275">Will your team be responsible for managing the automation platform as well?</span></span>

#### <a name="dsc-configurations"></a><span data-ttu-id="9dc81-276">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="9dc81-276">DSC configurations</span></span>

<span data-ttu-id="9dc81-277">Опрашивающий сервер предназначен для предоставления централизованного механизма для распределения конфигураций DSC на клиентские узлы.</span><span class="sxs-lookup"><span data-stu-id="9dc81-277">The purpose of a pull server is to provide a centralized mechanism for distributing DSC configurations to client nodes.</span></span> <span data-ttu-id="9dc81-278">Конфигурации хранятся на сервере в виде документов MOF.</span><span class="sxs-lookup"><span data-stu-id="9dc81-278">The configurations are stored on the server as MOF documents.</span></span> <span data-ttu-id="9dc81-279">Каждый документ получит название с уникальным идентификатором **GUID**.</span><span class="sxs-lookup"><span data-stu-id="9dc81-279">Each document will be named with a unique **Guid**.</span></span> <span data-ttu-id="9dc81-280">В ходе настройки клиентов на подключение к опрашиваемому серверу им также назначается идентификатор **GUID** конфигурации, которую они должны запросить.</span><span class="sxs-lookup"><span data-stu-id="9dc81-280">When clients are configured to connect with a pull server, they are also given the **Guid** for the configuration they should request.</span></span> <span data-ttu-id="9dc81-281">Эта система ссылок на конфигурации по идентификатору **GUID** гарантирует глобальную уникальность и является гибкой, поэтому конфигурация может применяться детализировано для каждого узла или в виде конфигурации роли, охватывающей несколько серверов, которые должны иметь одинаковые настройки.</span><span class="sxs-lookup"><span data-stu-id="9dc81-281">This system of referencing configurations by **Guid** guarantees global uniqueness and is flexible such that a configuration can be applied with granularity per node, or as a role configuration that spans many servers that should have identical configurations.</span></span>

#### <a name="guids"></a><span data-ttu-id="9dc81-282">Идентификаторы GUID</span><span class="sxs-lookup"><span data-stu-id="9dc81-282">Guids</span></span>

<span data-ttu-id="9dc81-283">Продумывая нюансы развертывания опрашивающего сервера, рекомендуется уделить особое внимание вопросу планирования реализации идентификаторов **GUID** в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9dc81-283">Planning for configuration **Guids** is worth additional attention when thinking through a pull server deployment.</span></span> <span data-ttu-id="9dc81-284">Особые требования к обработке идентификаторов **GUID** отсутствуют, и процесс, скорее всего, будет уникален и будет зависеть от конкретной среды.</span><span class="sxs-lookup"><span data-stu-id="9dc81-284">There is no specific requirement for how to handle **Guids** and the process is likely to be unique for each environment.</span></span> <span data-ttu-id="9dc81-285">Он может быть простым или же весьма сложным: централизованно хранимый CSV-файл, простая таблица SQL, база данных управления конфигурацией (CMDB), либо сложное решение, требующее интеграции с другим инструментом или программным решением.</span><span class="sxs-lookup"><span data-stu-id="9dc81-285">The process can range from simple to complex: a centrally stored CSV file, a simple SQL table, a CMDB, or a complex solution requiring integration with another tool or software solution.</span></span> <span data-ttu-id="9dc81-286">Существует два общих подхода, описанных далее.</span><span class="sxs-lookup"><span data-stu-id="9dc81-286">There are two general approaches:</span></span>

- <span data-ttu-id="9dc81-287">**Назначение идентификаторов GUID каждому серверу** — гарантируется, что конфигурация каждого сервера управляется отдельно.</span><span class="sxs-lookup"><span data-stu-id="9dc81-287">**Assigning Guids per server** — Provides a measure of assurance that every server configuration is controlled individually.</span></span> <span data-ttu-id="9dc81-288">Этот вариант обеспечивает определенный уровень точности, когда речь идет об обновлениях, и хорошо подходит для сред с небольшим числом серверов.</span><span class="sxs-lookup"><span data-stu-id="9dc81-288">This provides a level of precision around updates and can work well in environments with few servers.</span></span>
- <span data-ttu-id="9dc81-289">**Назначение идентификаторов GUID каждой роли сервера** — все серверы, которые выполняют одну и ту же функцию, например, веб-серверы, используют один и тот же идентификатор GUID для ссылки на необходимые данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9dc81-289">**Assigning Guids per server role** — All servers that perform the same function, such as web servers, use the same GUID to reference the required configuration data.</span></span> <span data-ttu-id="9dc81-290">Необходимо иметь в виду, что если идентификатор GUID является общим для множества серверов, все они будут обновлены одновременно в случае изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9dc81-290">Be aware that if many servers share the same GUID, all of them would be updated simultaneously when the configuration changes.</span></span>

  <span data-ttu-id="9dc81-291">Идентификатор GUID следует воспринимать как конфиденциальные данные, так как злоумышленники могут использовать его для получения данных о развертывании и настройке серверов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="9dc81-291">The GUID is something that should be considered sensitive data because it could be leveraged by someone with malicious intent to gain intelligence about how servers are deployed and configured in your environment.</span></span> <span data-ttu-id="9dc81-292">Дополнительные сведения см. в статье [Securely allocating GUIDs in PowerShell Desired State Configuration Pull Mode](https://blogs.msdn.microsoft.com/powershell/2014/12/31/securely-allocating-guids-in-powershell-desired-state-configuration-pull-mode/) (Безопасное выделение идентификаторов GUID в режиме запроса настройки требуемого состояния в PowerShell).</span><span class="sxs-lookup"><span data-stu-id="9dc81-292">For more information, see [Securely allocating Guids in PowerShell Desired State Configuration Pull Mode](https://blogs.msdn.microsoft.com/powershell/2014/12/31/securely-allocating-guids-in-powershell-desired-state-configuration-pull-mode/).</span></span>

<span data-ttu-id="9dc81-293">Задача по планированию</span><span class="sxs-lookup"><span data-stu-id="9dc81-293">Planning task</span></span>

- <span data-ttu-id="9dc81-294">Кто будет отвечать за копирование готовых конфигураций в папку опрашивающего сервера?</span><span class="sxs-lookup"><span data-stu-id="9dc81-294">Who will be responsible for copying configurations in to the pull server folder when they are ready?</span></span>
- <span data-ttu-id="9dc81-295">В чем будет заключаться процесс передачи конфигураций, создаваемых рабочей группой по разработке приложений?</span><span class="sxs-lookup"><span data-stu-id="9dc81-295">If Configurations are authored by an application team, what will the process be to hand them off?</span></span>
- <span data-ttu-id="9dc81-296">Будете ли вы использовать репозиторий для хранения создаваемых группами конфигураций?</span><span class="sxs-lookup"><span data-stu-id="9dc81-296">Will you leverage a repository to store configurations as they are being authored, across teams?</span></span>
- <span data-ttu-id="9dc81-297">Будет ли автоматизирован процесс копирования готовых конфигураций на сервер и создания контрольной суммы?</span><span class="sxs-lookup"><span data-stu-id="9dc81-297">Will you automate the process of copying configurations to the server and creating a checksum when they are ready?</span></span>
- <span data-ttu-id="9dc81-298">Как идентификаторы GUID будут сопоставляться с серверами или ролями и где они будут храниться?</span><span class="sxs-lookup"><span data-stu-id="9dc81-298">How will you map Guids to servers or roles, and where will this be stored?</span></span>
- <span data-ttu-id="9dc81-299">В чем будет заключаться процесс настройки клиентских компьютеров и каким образом он будет интегрирован с процессом создания и хранения идентификаторов GUID конфигурации?</span><span class="sxs-lookup"><span data-stu-id="9dc81-299">What will you use as a process to configure client machines, and how will it integrate with your process for creating and storing Configuration Guids?</span></span>

## <a name="installation-guide"></a><span data-ttu-id="9dc81-300">Руководство по установке</span><span class="sxs-lookup"><span data-stu-id="9dc81-300">Installation Guide</span></span>

<span data-ttu-id="9dc81-301">*Скрипты, приведенные в этом документе, относятся к категории стабильного кода. Всегда внимательно проверяйте скрипты перед их использованием в рабочей среде.*</span><span class="sxs-lookup"><span data-stu-id="9dc81-301">*Scripts given in this document are stable examples. Always review scripts carefully before executing them in a production environment.*</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9dc81-302">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9dc81-302">Prerequisites</span></span>

<span data-ttu-id="9dc81-303">Чтобы проверить версию PowerShell на сервере, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9dc81-303">To verify the version of PowerShell on your server use the following command.</span></span>

```powershell
$PSVersionTable.PSVersion
```

<span data-ttu-id="9dc81-304">Если возможно, обновитесь до последней версии Windows Management Framework.</span><span class="sxs-lookup"><span data-stu-id="9dc81-304">If possible, upgrade to the latest version of Windows Management Framework.</span></span> <span data-ttu-id="9dc81-305">Затем скачайте модуль `xPsDesiredStateConfiguration`, используя следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9dc81-305">Next, download the `xPsDesiredStateConfiguration` module using the following command.</span></span>

```powershell
Install-Module xPSDesiredStateConfiguration
```

<span data-ttu-id="9dc81-306">Перед скачиванием команда запросит у вас подтверждение.</span><span class="sxs-lookup"><span data-stu-id="9dc81-306">The command will ask for your approval before downloading the module.</span></span>

### <a name="installation-and-configuration-scripts"></a><span data-ttu-id="9dc81-307">Скрипты для установки и настройки</span><span class="sxs-lookup"><span data-stu-id="9dc81-307">Installation and configuration scripts</span></span>

<span data-ttu-id="9dc81-308">Лучшим способом развертывания опрашивающего сервера DSC является использование скрипта настройки DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-308">The best method to deploy a DSC pull server is to use a DSC configuration script.</span></span> <span data-ttu-id="9dc81-309">В этом документе представлены скрипты, включающие как основные параметры, применяемые для настройки только веб-службы DSC, так и дополнительные параметры, применяемые для полной настройки Windows Server и веб-службы DSC.</span><span class="sxs-lookup"><span data-stu-id="9dc81-309">This document will present scripts including both basic settings that would configure only the DSC web service and advanced settings that would configure a Windows Server end-to-end including DSC web service.</span></span>

<span data-ttu-id="9dc81-310">Примечание.  Сейчас для работы модуля DSC `xPSDesiredStateConfiguration` требуется, чтобы на сервере использовался английский язык (EN-US).</span><span class="sxs-lookup"><span data-stu-id="9dc81-310">Note:  Currently the `xPSDesiredStateConfiguration` DSC module requires the server to be EN-US locale.</span></span>

### <a name="basic-configuration-for-windows-server-2012"></a><span data-ttu-id="9dc81-311">Базовая настройка Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9dc81-311">Basic configuration for Windows Server 2012</span></span>

```powershell
# This is a very basic Configuration to deploy a pull server instance in a lab environment on Windows Server 2012.

Configuration PullServer {
Import-DscResource -ModuleName xPSDesiredStateConfiguration

        # Load the Windows Server DSC Service feature
        WindowsFeature DSCServiceFeature
        {
          Ensure = 'Present'
          Name = 'DSC-Service'
        }

        # Use the DSC Resource to simplify deployment of the web service
        xDSCWebService PSDSCPullServer
        {
          Ensure = 'Present'
          EndpointName = 'PSDSCPullServer'
          Port = 8080
          PhysicalPath = "$env:SYSTEMDRIVE\inetpub\wwwroot\PSDSCPullServer"
          CertificateThumbPrint = 'AllowUnencryptedTraffic'
          ModulePath = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
          ConfigurationPath = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
          State = 'Started'
          DependsOn = '[WindowsFeature]DSCServiceFeature'
        }
}
PullServer -OutputPath 'C:\PullServerConfig\'
Start-DscConfiguration -Wait -Force -Verbose -Path 'C:\PullServerConfig\'
```

### <a name="advanced-configuration-for-windows-server-2012-r2"></a><span data-ttu-id="9dc81-312">Расширенная настройка Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9dc81-312">Advanced configuration for Windows Server 2012 R2</span></span>

```powershell
# This is an advanced Configuration example for Pull Server production deployments
# on Windows Server 2012 R2. Many of the features demonstrated are optional and
# provided to demonstrate how to adapt the Configuration for multiple scenarios
# Select the needed resources based on the requirements for each environment.
# Optional scenarios include:
#      * Reduce footprint to Server Core
#      * Rename server and join domain
#      * Switch from SSL to TLS for HTTPS
#      * Automatically load certificate from Certificate Authority
#      * Locate Modules and Configuration data on remote SMB share
#      * Manage state of default websites in IIS

param (
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [System.String] $ServerName,
        [System.String] $DomainName,
        [System.String] $CARootName,
        [System.String] $CAServerFQDN,
        [System.String] $CertSubject,
        [System.String] $SMBShare,
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $Credential
    )

Configuration PullServer {
    Import-DscResource -ModuleName xPSDesiredStateConfiguration, xWebAdministration, xCertificate, xComputerManagement
    Node localhost
    {

        # Configure the server to automatically corret configuration drift including reboots if needed.
        LocalConfigurationManager
        {
            ConfigurationMode = 'ApplyAndAutoCorrect'
            RebootNodeifNeeded = $node.RebootNodeifNeeded
            CertificateId = $node.Thumbprint
        }

        # Remove all GUI interfaces so the server has minimum running footprint.
        WindowsFeature ServerCore
        {
            Ensure = 'Absent'
            Name = 'User-Interfaces-Infra'
        }

        # Set the server name and if needed, join a domain. If not joining a domain, remove the DomainName parameter.
        xComputer DomainJoin
        {
            Name = $Node.ServerName
            DomainName = $Node.DomainName
            Credential = $Node.Credential
        }

        # The next series of settings disable SSL and enable TLS, for environments where that is required by policy.
        Registry TLS1_2ServerEnabled
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server'
            ValueName = 'Enabled'
            ValueData = 1
            ValueType = 'Dword'
        }

        Registry TLS1_2ServerDisabledByDefault
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server'
            ValueName = 'DisabledByDefault'
            ValueData = 0
            ValueType = 'Dword'
        }

        Registry TLS1_2ClientEnabled
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client'
            ValueName = 'Enabled'
            ValueData = 1
            ValueType = 'Dword'
        }

        Registry TLS1_2ClientDisabledByDefault
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client'
            ValueName = 'DisabledByDefault'
            ValueData = 0
            ValueType = 'Dword'
        }

        Registry SSL2ServerDisabled
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server'
            ValueName = 'Enabled'
            ValueData = 0
            ValueType = 'Dword'
        }

        # Install the Windows Server DSC Service feature
        WindowsFeature DSCServiceFeature
        {
            Ensure = 'Present'
            Name = 'DSC-Service'
        }

        # If using a certificate from a local Active Directory Enterprise Root Certificate Authority,
        # complete a request and install the certificate
        xCertReq SSLCert
        {
            CARootName = $Node.CARootName
            CAServerFQDN = $Node.CAServerFQDN
            Subject = $Node.CertSubject
            AutoRenew = $Node.AutoRenew
            Credential = $Node.Credential
        }

        # Use the DSC resource to simplify deployment of the web service.  You might also consider
        # modifying the default port, possibly leveraging port 443 in environments where that is
        # enforced as a standard.
        xDSCWebService PSDSCPullServer
        {
            Ensure = 'Present'
            EndpointName = 'PSDSCPullServer'
            Port = 8080
            PhysicalPath = "$env:SYSTEMDRIVE\inetpub\wwwroot\PSDSCPullServer"
            CertificateThumbPrint = 'CertificateSubject'
            CertificateSubject = $Node.CertSubject
            ModulePath = "$($Node.SMBShare)\DscService\Modules"
            ConfigurationPath = "$($Node.SMBShare)\DscService\Configuration"
            State = 'Started'
            DependsOn = '[WindowsFeature]DSCServiceFeature'
        }

        # Validate web config file contains current DB settings
        xWebConfigKeyValue CorrectDBProvider
        {
            ConfigSection = 'AppSettings'
            Key = 'dbprovider'
            Value = 'System.Data.OleDb'
            WebsitePath = 'IIS:\sites\PSDSCPullServer'
            DependsOn = '[xDSCWebService]PSDSCPullServer'
        }
        xWebConfigKeyValue CorrectDBConnectionStr
        {
            ConfigSection = 'AppSettings'
            Key = 'dbconnectionstr'
            Value = 'Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Program Files\WindowsPowerShell\DscService\Devices.mdb;'
            WebsitePath = 'IIS:\sites\PSDSCPullServer'
            DependsOn = '[xDSCWebService]PSDSCPullServer'
        }

        # Stop the default website
        xWebsite StopDefaultSite
        {
            Ensure = 'Present'
            Name = 'Default Web Site'
            State = 'Stopped'
            PhysicalPath = 'C:\inetpub\wwwroot'
            DependsOn = '[WindowsFeature]DSCServiceFeature'
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            ServerName = $ServerName
            DomainName = $DomainName
            CARootName = $CARootName
            CAServerFQDN = $CAServerFQDN
            CertSubject = $CertSubject
            AutoRenew = $true
            SMBShare = $SMBShare
            Credential = $Credential
            RebootNodeifNeeded = $true
            CertificateFile = 'c:\PullServerConfig\Cert.cer'
            Thumbprint = 'B9A39921918B466EB1ADF2509E00F5DECB2EFDA9'
            }
        )
    }

PullServer -ConfigurationData $configData -OutputPath 'C:\PullServerConfig\'
Set-DscLocalConfigurationManager -ComputerName localhost -Path 'C:\PullServerConfig\'
Start-DscConfiguration -Wait -Force -Verbose -Path 'C:\PullServerConfig\'

# .\Script.ps1 -ServerName web1 -domainname 'test.pha' -carootname 'test-dc01-ca' -caserverfqdn 'dc01.test.pha' -certsubject 'CN=service.test.pha' -smbshare '\\sofs1.test.pha\share'
```

### <a name="verify-pull-server-functionality"></a><span data-ttu-id="9dc81-313">Проверка работоспособности опрашивающего сервера</span><span class="sxs-lookup"><span data-stu-id="9dc81-313">Verify pull server functionality</span></span>

```powershell
# This function is meant to simplify a check against a DSC pull server. If you do not use the
# default service URL, you will need to adjust accordingly.
function Verify-DSCPullServer ($fqdn) {
    ([xml](Invoke-WebRequest "https://$($fqdn):8080/psdscpullserver.svc" | % Content)).service.workspace.collection.href
}

Verify-DSCPullServer 'INSERT SERVER FQDN'
```

```output
Expected Result:
Action
Module
StatusReport
Node
```

### <a name="configure-clients"></a><span data-ttu-id="9dc81-314">Настройка клиентов</span><span class="sxs-lookup"><span data-stu-id="9dc81-314">Configure clients</span></span>

```powershell
Configuration PullClient {
    param(
    $ID,
    $Server
    )
        LocalConfigurationManager
                {
                    ConfigurationID = $ID;
                    RefreshMode = 'PULL';
                    DownloadManagerName = 'WebDownloadManager';
                    RebootNodeIfNeeded = $true;
                    RefreshFrequencyMins = 30;
                    ConfigurationModeFrequencyMins = 15;
                    ConfigurationMode = 'ApplyAndAutoCorrect';
                    DownloadManagerCustomData = @{ServerUrl = "http://"+$Server+":8080/PSDSCPullServer.svc"; AllowUnsecureConnection = $true}
                }
}

PullClient -ID 'INSERTGUID' -Server 'INSERTSERVER' -Output 'C:\DSCConfig\'
Set-DscLocalConfigurationManager -ComputerName 'Localhost' -Path 'C:\DSCConfig\' -Verbose
```

## <a name="additional-references-snippets-and-examples"></a><span data-ttu-id="9dc81-315">Дополнительные материалы, фрагменты кода и примеры</span><span class="sxs-lookup"><span data-stu-id="9dc81-315">Additional references, snippets, and examples</span></span>

<span data-ttu-id="9dc81-316">В этом примере показано, как вручную установить подключение к клиенту (требуется WMF5) для тестирования.</span><span class="sxs-lookup"><span data-stu-id="9dc81-316">This example shows how to manually initiate a client connection (requires WMF5) for testing.</span></span>

```powershell
Update-DscConfiguration –Wait -Verbose
```

<span data-ttu-id="9dc81-317">Командлет [Add-DnsServerResourceRecordName](/powershell/module/dnsserver/add-dnsserverresourcerecordcname) используется для добавления записи CNAME типа в зону DNS.</span><span class="sxs-lookup"><span data-stu-id="9dc81-317">The [Add-DnsServerResourceRecordName](/powershell/module/dnsserver/add-dnsserverresourcerecordcname) cmdlet is used to add a type CNAME record to a DNS zone.</span></span>

<span data-ttu-id="9dc81-318">Функция PowerShell для [создания контрольной суммы и публикации MOF-файлов DSC на опрашивающем SMB-сервере](https://gallery.technet.microsoft.com/scriptcenter/PowerShell-Function-to-3bc4b7f0) автоматически создает необходимую контрольную сумму, а затем копирует MOF-файлы конфигурации и файлы контрольной суммы на опрашивающий SMB-сервер.</span><span class="sxs-lookup"><span data-stu-id="9dc81-318">The PowerShell Function to [Create a Checksum and Publish DSC MOF to SMB Pull Server](https://gallery.technet.microsoft.com/scriptcenter/PowerShell-Function-to-3bc4b7f0) automatically generates the required checksum, and then copies both the MOF configuration and checksum files to the SMB pull server.</span></span>

## <a name="appendix---understanding-odata-service-data-file-types"></a><span data-ttu-id="9dc81-319">Приложение. Основные сведения о типах файлов данных службы ODATA</span><span class="sxs-lookup"><span data-stu-id="9dc81-319">Appendix - Understanding ODATA service data file types</span></span>

<span data-ttu-id="9dc81-320">Файл данных хранится для создания информации во время развертывания опрашивающего сервера, в состав которого входит веб-служба OData.</span><span class="sxs-lookup"><span data-stu-id="9dc81-320">A data file is stored to create information during deployment of a pull server that includes the OData web service.</span></span> <span data-ttu-id="9dc81-321">Тип файла зависит от операционной системы, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="9dc81-321">The type of file depends on the operating system, as described below.</span></span>

- <span data-ttu-id="9dc81-322">**Windows Server 2012** Файл всегда будет иметь тип MDB.</span><span class="sxs-lookup"><span data-stu-id="9dc81-322">**Windows Server 2012** The file type will always be   .mdb</span></span>
- <span data-ttu-id="9dc81-323">**Windows Server 2012 R2** Файл по умолчанию будет иметь тип EDB до тех пор, пока в конфигурации не будет указан тип MBD.</span><span class="sxs-lookup"><span data-stu-id="9dc81-323">**Windows Server 2012 R2** The file type will default to .edb unless a .mdb is specified in the configuration</span></span>

<span data-ttu-id="9dc81-324">В [скрипте-примере расширенной конфигурации](https://github.com/mgreenegit/Whitepapers/blob/Dev/PullServerCPIG.md#installation-and-configuration-scripts) по установке опрашивающего сервера также демонстрируется автоматическое управление параметрами файла web.config для предотвращения ошибок, вызванных типом файла.</span><span class="sxs-lookup"><span data-stu-id="9dc81-324">In the [Advanced example script](https://github.com/mgreenegit/Whitepapers/blob/Dev/PullServerCPIG.md#installation-and-configuration-scripts) for installing a Pull Server, you will also find an example of how to automatically control the web.config file settings to prevent any chance of error caused by file type.</span></span>
