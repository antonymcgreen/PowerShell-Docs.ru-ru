---
ms.date: 08/15/2019
keywords: dsc,powershell,конфигурация,установка
title: Начало работы с Desired State Configuration (DSC) для Windows
description: В этом разделе объясняется, как приступить к работе с Desired State Configuration (DSC) в PowerShell для Windows.
ms.openlocfilehash: 2b9ddba2023a3933e3ad70d7bfee798ff07f0484
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662813"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="a5d7a-104">Начало работы с Desired State Configuration (DSC) для Windows</span><span class="sxs-lookup"><span data-stu-id="a5d7a-104">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="a5d7a-105">В этом разделе объясняется, как приступить к работе с Desired State Configuration (DSC) в PowerShell для Windows.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-105">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span> <span data-ttu-id="a5d7a-106">Общие сведения о службе настройки требуемого состояния см. в разделе [Начало работы со службой настройки требуемого состояния Windows PowerShell](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5d7a-106">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="a5d7a-107">Поддерживаемые версии операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="a5d7a-107">Supported Windows operation system versions</span></span>

<span data-ttu-id="a5d7a-108">Поддерживаются следующие версии:</span><span class="sxs-lookup"><span data-stu-id="a5d7a-108">The following versions are supported:</span></span>

- <span data-ttu-id="a5d7a-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5d7a-109">Windows Server 2019</span></span>
- <span data-ttu-id="a5d7a-110">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a5d7a-110">Windows Server 2016</span></span>
- <span data-ttu-id="a5d7a-111">Windows Server 2012 R2;</span><span class="sxs-lookup"><span data-stu-id="a5d7a-111">Windows Server 2012R2</span></span>
- <span data-ttu-id="a5d7a-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a5d7a-112">Windows Server 2012</span></span>
- <span data-ttu-id="a5d7a-113">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="a5d7a-113">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="a5d7a-114">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a5d7a-114">Windows 10</span></span>
- <span data-ttu-id="a5d7a-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a5d7a-115">Windows 8.1</span></span>
- <span data-ttu-id="a5d7a-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="a5d7a-116">Windows 7</span></span>

<span data-ttu-id="a5d7a-117">Номер SKU автономного продукта [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) не содержит реализацию Desired State Configuration, поэтому управлять им с помощью DSC PowerShell или настройки состояния службы автоматизации Azure невозможно.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-117">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku doesn't contain an implementation of Desired State Configuration so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="a5d7a-118">Установка DSC</span><span class="sxs-lookup"><span data-stu-id="a5d7a-118">Installing DSC</span></span>

<span data-ttu-id="a5d7a-119">Desired State Configuration в PowerShell входит в состав Windows и обновляется с помощью Windows Management Framework.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-119">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span> <span data-ttu-id="a5d7a-120">Последняя версия — [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="a5d7a-120">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="a5d7a-121">Для управления компьютером с помощью DSC не нужно включать компонент Windows Server "DSC-Service".</span><span class="sxs-lookup"><span data-stu-id="a5d7a-121">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="a5d7a-122">Этот компонент необходим только при создании экземпляра опрашиваемого сервера Windows.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-122">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="a5d7a-123">Использование DSC для Windows</span><span class="sxs-lookup"><span data-stu-id="a5d7a-123">Using DSC for Windows</span></span>

<span data-ttu-id="a5d7a-124">В следующих разделах описывается создание и запуск конфигураций DSC на компьютерах Windows.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-124">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="a5d7a-125">Создание MOF-документа конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5d7a-125">Creating a configuration MOF document</span></span>

<span data-ttu-id="a5d7a-126">Для создания конфигурации используется ключевое слово Windows PowerShell (`Configuration`).</span><span class="sxs-lookup"><span data-stu-id="a5d7a-126">The Windows PowerShell `Configuration` keyword is used to create a configuration.</span></span>
<span data-ttu-id="a5d7a-127">В инструкциях ниже описывается создание документа конфигурации с использованием Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-127">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="a5d7a-128">Определите конфигурацию и создайте документ конфигурации:</span><span class="sxs-lookup"><span data-stu-id="a5d7a-128">Define a configuration and generate the configuration document:</span></span>

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

#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="a5d7a-129">Установка модуля, содержащего ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="a5d7a-129">Install a module containing DSC resources</span></span>

<span data-ttu-id="a5d7a-130">Desired State Configuration в Windows PowerShell включает встроенные модули, содержащие ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-130">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="a5d7a-131">Модули также можно загружать из внешних источников, таких как коллекция PowerShell, с помощью командлетов PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-131">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="a5d7a-132">Применение конфигурации к компьютеру</span><span class="sxs-lookup"><span data-stu-id="a5d7a-132">Apply the configuration to the machine</span></span>

> [!NOTE]
> <span data-ttu-id="a5d7a-133">Чтобы разрешить выполнение DSC, Windows необходимо настроить для получения удаленных команд PowerShell, даже когда вы запускаете конфигурацию `localhost`.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-133">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="a5d7a-134">Чтобы правильно настроить среду, запустите `Set-WsManQuickConfig -Force` в терминале PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-134">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="a5d7a-135">Документы конфигурации (MOF-файлы) можно применить к компьютеру с помощью командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="a5d7a-135">Configuration documents (MOF files) can be applied to the machineusing the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="a5d7a-136">Получение данных о текущем состоянии конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5d7a-136">Get the current state of the configuration</span></span>

<span data-ttu-id="a5d7a-137">Командлет [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) запрашивает текущее состояние компьютера и возвращает текущие значения для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-137">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

```powershell
Get-DscConfiguration
```

<span data-ttu-id="a5d7a-138">Командлет [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) возвращает текущую метаконфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-138">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="a5d7a-139">Удаление текущей конфигурации с компьютера</span><span class="sxs-lookup"><span data-stu-id="a5d7a-139">Remove the current configuration from a machine</span></span>

<span data-ttu-id="a5d7a-140">Командлет [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument).</span><span class="sxs-lookup"><span data-stu-id="a5d7a-140">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="a5d7a-141">Настройка параметров в локальном диспетчере конфигураций</span><span class="sxs-lookup"><span data-stu-id="a5d7a-141">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="a5d7a-142">Примените MOF-файл метаконфигурации к компьютеру с помощью командлета [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="a5d7a-142">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="a5d7a-143">При этом потребуется указать путь к соответствующему MOF-файлу метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-143">Requires the path to the Meta Configuration MOF.</span></span>

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="a5d7a-144">Файлы журнала Desired State Configuration в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5d7a-144">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="a5d7a-145">Журналы DSC записываются в журнал событий Windows по пути `Microsoft-Windows-Dsc/Operational`.</span><span class="sxs-lookup"><span data-stu-id="a5d7a-145">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="a5d7a-146">Дополнительные журналы для отладки можно включить, выполнив действия, описанные в разделе [Где находятся журналы событий DSC?](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)</span><span class="sxs-lookup"><span data-stu-id="a5d7a-146">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
