---
ms.date: 08/15/2019
keywords: dsc,powershell,конфигурация,установка
title: Начало работы с Desired State Configuration (DSC) для Windows
ms.openlocfilehash: a4f9db481afda65fc4ac5e553230dbba3037ac9a
ms.sourcegitcommit: 5a004064f33acc0145ccd414535763e95f998c89
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988872"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="ffb72-103">Начало работы с Desired State Configuration (DSC) для Windows</span><span class="sxs-lookup"><span data-stu-id="ffb72-103">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="ffb72-104">В этом разделе объясняется, как приступить к работе с Desired State Configuration (DSC) в PowerShell для Windows.</span><span class="sxs-lookup"><span data-stu-id="ffb72-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span>
<span data-ttu-id="ffb72-105">Общие сведения о службе настройки требуемого состояния см. в разделе [Начало работы со службой настройки требуемого состояния Windows PowerShell](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ffb72-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="ffb72-106">Поддерживаемые версии операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="ffb72-106">Supported Windows operation system versions</span></span>

<span data-ttu-id="ffb72-107">Поддерживаются следующие версии:</span><span class="sxs-lookup"><span data-stu-id="ffb72-107">The following versions are supported:</span></span>

- <span data-ttu-id="ffb72-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="ffb72-108">Windows Server 2019</span></span>
- <span data-ttu-id="ffb72-109">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ffb72-109">Windows Server 2016</span></span>
- <span data-ttu-id="ffb72-110">Windows Server 2012 R2;</span><span class="sxs-lookup"><span data-stu-id="ffb72-110">Windows Server 2012R2</span></span>
- <span data-ttu-id="ffb72-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ffb72-111">Windows Server 2012</span></span>
- <span data-ttu-id="ffb72-112">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="ffb72-112">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="ffb72-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ffb72-113">Windows 10</span></span>
- <span data-ttu-id="ffb72-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ffb72-114">Windows 8.1</span></span>
- <span data-ttu-id="ffb72-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ffb72-115">Windows 7</span></span>

<span data-ttu-id="ffb72-116">Номер SKU автономного продукта [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) не содержит реализацию Desired State Configuration, поэтому управлять им с помощью DSC PowerShell или настройки состояния службы автоматизации Azure невозможно.</span><span class="sxs-lookup"><span data-stu-id="ffb72-116">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku does not contain an implementation of Desired State Configuraion so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="ffb72-117">Установка DSC</span><span class="sxs-lookup"><span data-stu-id="ffb72-117">Installing DSC</span></span>

<span data-ttu-id="ffb72-118">Desired State Configuration в PowerShell входит в состав Windows и обновляется с помощью Windows Management Framework.</span><span class="sxs-lookup"><span data-stu-id="ffb72-118">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span>
<span data-ttu-id="ffb72-119">Последняя версия — [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="ffb72-119">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="ffb72-120">Для управления компьютером с помощью DSC не нужно включать компонент Windows Server "DSC-Service".</span><span class="sxs-lookup"><span data-stu-id="ffb72-120">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="ffb72-121">Этот компонент необходим только при создании экземпляра опрашиваемого сервера Windows.</span><span class="sxs-lookup"><span data-stu-id="ffb72-121">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="ffb72-122">Использование DSC для Windows</span><span class="sxs-lookup"><span data-stu-id="ffb72-122">Using DSC for Windows</span></span>

<span data-ttu-id="ffb72-123">В следующих разделах описывается создание и запуск конфигураций DSC на компьютерах Windows.</span><span class="sxs-lookup"><span data-stu-id="ffb72-123">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="ffb72-124">Создание MOF-документа конфигурации</span><span class="sxs-lookup"><span data-stu-id="ffb72-124">Creating a configuration MOF document</span></span>

<span data-ttu-id="ffb72-125">Для создания конфигурации используется ключевое слово конфигурации Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffb72-125">The Windows PowerShell Configuration keyword is used to create a configuration.</span></span>
<span data-ttu-id="ffb72-126">В инструкциях ниже описывается создание документа конфигурации с использованием Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffb72-126">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="ffb72-127">Определите конфигурацию и создайте документ конфигурации:</span><span class="sxs-lookup"><span data-stu-id="ffb72-127">Define a configuration and generate the configuration document:</span></span>

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```
#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="ffb72-128">Установка модуля, содержащего ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="ffb72-128">Install a module containing DSC resources</span></span>

<span data-ttu-id="ffb72-129">Desired State Configuration в Windows PowerShell включает встроенные модули, содержащие ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="ffb72-129">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="ffb72-130">Модули также можно загружать из внешних источников, таких как коллекция PowerShell, с помощью командлетов PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="ffb72-130">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

`Install-Module 'PSDscResources' -Verbose`

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="ffb72-131">Применение конфигурации к компьютеру</span><span class="sxs-lookup"><span data-stu-id="ffb72-131">Apply the configuration to the machine</span></span>

<span data-ttu-id="ffb72-132">Документы конфигурации (MOF-файлы) можно применить к компьютеру с помощью командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="ffb72-132">Configuration documents (MOF files) can be applied to the machine using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

`Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose`

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="ffb72-133">Получение данных о текущем состоянии конфигурации</span><span class="sxs-lookup"><span data-stu-id="ffb72-133">Get the current state of the configuration</span></span>

<span data-ttu-id="ffb72-134">Командлет [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) запрашивает текущее состояние компьютера и возвращает текущие значения для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ffb72-134">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

`Get-DscConfiguration`

<span data-ttu-id="ffb72-135">Командлет [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) возвращает текущую метаконфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ffb72-135">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

`Get-DscLocalConfigurationManager`

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="ffb72-136">Удаление текущей конфигурации с компьютера</span><span class="sxs-lookup"><span data-stu-id="ffb72-136">Remove the current configuration from a machine</span></span>

<span data-ttu-id="ffb72-137">Командлет [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument).</span><span class="sxs-lookup"><span data-stu-id="ffb72-137">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

`Remove-DscConfigurationDocument -Stage Current -Verbose`

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="ffb72-138">Настройка параметров в локальном диспетчере конфигураций</span><span class="sxs-lookup"><span data-stu-id="ffb72-138">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="ffb72-139">Примените MOF-файл метаконфигурации к компьютеру с помощью командлета [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="ffb72-139">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span>
<span data-ttu-id="ffb72-140">При этом потребуется указать путь к соответствующему MOF-файлу метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="ffb72-140">Requires the path to the Meta Configuration MOF.</span></span>

`Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose`

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="ffb72-141">Файлы журнала Desired State Configuration в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffb72-141">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="ffb72-142">Журналы DSC записываются в журнал событий Windows по пути `Microsoft-Windows-Dsc/Operational`.</span><span class="sxs-lookup"><span data-stu-id="ffb72-142">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="ffb72-143">Дополнительные журналы для отладки можно включить, выполнив действия, описанные в разделе [Где находятся журналы событий DSC?](/powershell/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)</span><span class="sxs-lookup"><span data-stu-id="ffb72-143">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
