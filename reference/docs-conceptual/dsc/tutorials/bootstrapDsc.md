---
ms.date: 11/09/2020
keywords: dsc,powershell,конфигурация,установка
title: Настройка виртуальных машин при начальной загрузке с помощью DSC
description: В этой статье описывается, как настроить виртуальную машину при начальной загрузке с помощью DSC.
ms.openlocfilehash: 09449053ff085209dec6ccbfa800e5d112d1c769
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390003"
---
# <a name="configure-a-virtual-machines-at-initial-boot-up-by-using-dsc"></a><span data-ttu-id="f7dcb-104">Настройка виртуальных машин при начальной загрузке с помощью DSC</span><span class="sxs-lookup"><span data-stu-id="f7dcb-104">Configure a virtual machines at initial boot-up by using DSC</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7dcb-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f7dcb-105">Applies To: Windows PowerShell 5.0</span></span>

## <a name="requirements"></a><span data-ttu-id="f7dcb-106">Требования</span><span class="sxs-lookup"><span data-stu-id="f7dcb-106">Requirements</span></span>

> [!NOTE]
> <span data-ttu-id="f7dcb-107">Раздел реестра **DSCAutomationHostEnabled**, описанный в этом разделе, недоступен в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-107">The **DSCAutomationHostEnabled** registry key described in this topic is not available in PowerShell 4.0.</span></span> <span data-ttu-id="f7dcb-108">Сведения о настройке новых виртуальных машин при начальной загрузке в PowerShell 4.0 см. в разделе [Требуется автоматически настроить машины с помощью DSC при начальной загрузке?](https://devblogs.microsoft.com/powershell/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-108">For information on how to configure new virtual machines at initial boot-up in PowerShell 4.0, see [Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://devblogs.microsoft.com/powershell/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span></span>

<span data-ttu-id="f7dcb-109">Для выполнения этих примеров требуется следующее.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-109">To run these examples, you will need:</span></span>

- <span data-ttu-id="f7dcb-110">Загрузочный VHD.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-110">A bootable VHD to work with.</span></span> <span data-ttu-id="f7dcb-111">ISO-файл с пробной версией Windows Server 2016 можно скачать в [Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-111">You can download an ISO with an evaluation copy of Windows Server 2016 at [Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016).</span></span>
  <span data-ttu-id="f7dcb-112">Инструкции по созданию VHD из ISO-образа см. в разделе [Создание загрузочных виртуальных жестких дисков](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-112">You can find instructions on how to create a VHD from an ISO image at [Creating Bootable Virtual Hard Disks](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span></span>
- <span data-ttu-id="f7dcb-113">Компьютер с включенным Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-113">A host computer that has Hyper-V enabled.</span></span> <span data-ttu-id="f7dcb-114">Дополнительные сведения см. в статье [Обзор Hyper-V](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-114">For information, see [Hyper-V overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span></span>

  <span data-ttu-id="f7dcb-115">С помощью DSC можно автоматизировать установку и настройку программного обеспечения для компьютера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-115">By using DSC, you can automate software installation and configuration for a computer at initial boot-up.</span></span> <span data-ttu-id="f7dcb-116">Для этого необходимо добавить документ MOF конфигурации или метаконфигурацию на загрузочный носитель (например, VHD), чтобы они выполнялись при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-116">You do this by either injecting a configuration MOF document or a metaconfiguration into bootable media (such as a VHD) so that they are run during the initial boot-up process.</span></span> <span data-ttu-id="f7dcb-117">Такое поведение контролируется [разделом реестра DSCAutomationHostEnabled](DSCAutomationHostEnabled.md) в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-117">This behavior is specified by the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key under `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span></span>
  <span data-ttu-id="f7dcb-118">По умолчанию значение этого раздела — 2, что позволяет DSC запускаться во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-118">By default, the value of this key is 2, which allows DSC to run at boot time.</span></span>

  <span data-ttu-id="f7dcb-119">Если запускать DSC во время загрузки не следует, задайте для [раздела реестра DSCAutomationHostEnabled](DSCAutomationHostEnabled.md) значение 0.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-119">If you do not want DSC to run at boot time, set the value of the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key to 0.</span></span>

- <span data-ttu-id="f7dcb-120">Добавление документа MOF конфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="f7dcb-120">Inject a configuration MOF document into a VHD</span></span>
- <span data-ttu-id="f7dcb-121">Добавление метаконфигурации DSC в VHD</span><span class="sxs-lookup"><span data-stu-id="f7dcb-121">Inject a DSC metaconfiguration into a VHD</span></span>
- <span data-ttu-id="f7dcb-122">Отключение DSC при загрузке</span><span class="sxs-lookup"><span data-stu-id="f7dcb-122">Disable DSC at boot time</span></span>

> [!NOTE]
> <span data-ttu-id="f7dcb-123">На компьютер можно одновременно добавить `Pending.mof` и `MetaConfig.mof`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-123">You can inject both `Pending.mof` and `MetaConfig.mof` into a computer at the same time.</span></span>
> <span data-ttu-id="f7dcb-124">Если присутствуют оба файла, более высокий приоритет имеют параметры, указанные в `MetaConfig.mof`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-124">If both files are present, the settings specified in `MetaConfig.mof` take precedence.</span></span>

## <a name="inject-a-configuration-mof-document-into-a-vhd"></a><span data-ttu-id="f7dcb-125">Добавление документа MOF конфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="f7dcb-125">Inject a configuration MOF document into a VHD</span></span>

<span data-ttu-id="f7dcb-126">Для применения конфигурации при начальной загрузке добавьте скомпилированный документ MOF конфигурации в VHD в качестве его файла `Pending.mof`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-126">To enact a configuration at initial boot-up, you can inject a compiled configuration MOF document into the VHD as its `Pending.mof` file.</span></span> <span data-ttu-id="f7dcb-127">Если раздел реестра **DSCAutomationHostEnabled** имеет значение 2 (значение по умолчанию), DSC применяет конфигурацию, определенную в `Pending.mof`, при первой загрузке компьютера.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-127">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the configuration defined by `Pending.mof` when the computer boots up for the first time.</span></span>

<span data-ttu-id="f7dcb-128">В этом примере используется следующая конфигурация, которая устанавливает службы IIS на новом компьютере.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-128">For this example, we will use the following configuration, which will install IIS on the new computer:</span></span>

```powershell
Configuration SampleIISInstall
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    node ('localhost')
    {
        WindowsFeature IIS
        {
            Ensure = 'Present'
            Name   = 'Web-Server'
        }
    }
}
```

### <a name="to-inject-the-configuration-mof-document-on-the-vhd"></a><span data-ttu-id="f7dcb-129">Добавление документа MOF конфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="f7dcb-129">To inject the configuration MOF document on the VHD</span></span>

1. <span data-ttu-id="f7dcb-130">Подключите VHD, в который нужно добавить конфигурацию, вызвав командлет [Mount-VHD](/powershell/module/hyper-v/mount-vhd).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-130">Mount the VHD into which you want to inject the configuration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="f7dcb-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="f7dcb-131">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="f7dcb-132">На компьютере с PowerShell 5.0 или более поздней версией сохраните указанную выше конфигурацию (**SampleIISInstall**) как файл сценария PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-132">On a computer running PowerShell 5.0 or later, save the above configuration (**SampleIISInstall**) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="f7dcb-133">В консоли PowerShell перейдите в папку, где был сохранен PS1-файл.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-133">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="f7dcb-134">Выполните следующие команды PowerShell для компиляции документа MOF (дополнительные сведения о компиляции конфигураций DSC см. в разделе [Конфигурации DSC](../configurations/configurations.md)).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-134">Run the following PowerShell commands to compile the MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\SampleIISInstall.ps1
   SampleIISInstall
   ```

1. <span data-ttu-id="f7dcb-135">Будет создан файл `localhost.mof` в новой папке с именем `SampleIISInstall`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-135">This will create a `localhost.mof` file in a new folder named `SampleIISInstall`.</span></span> <span data-ttu-id="f7dcb-136">Переименуйте и переместите этот файл в нужное место на VHD как `Pending.mof` при помощи командлета [Move-Item](/powershell/module/microsoft.powershell.management/move-item).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-136">Rename and move that file into the proper location on the VHD as `Pending.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span> <span data-ttu-id="f7dcb-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="f7dcb-137">For example:</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\SampleIISInstall\localhost.mof -Destination E:\Windows\System32\Configuration\Pending.mof
   ```

1. <span data-ttu-id="f7dcb-138">Отключите VHD, вызвав командлет [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-138">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="f7dcb-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="f7dcb-139">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="f7dcb-140">Создайте виртуальную машину с помощью VHD, на который установлен документ MOF DSC.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-140">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="f7dcb-141">После первоначальной загрузки и установки операционной системы будут установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-141">After initial boot-up and operating system installation, IIS will be installed.</span></span> <span data-ttu-id="f7dcb-142">Это можно проверить, вызвав командлет [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-142">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="inject-a-dsc-metaconfiguration-into-a-vhd"></a><span data-ttu-id="f7dcb-143">Добавление метаконфигурации DSC в VHD</span><span class="sxs-lookup"><span data-stu-id="f7dcb-143">Inject a DSC metaconfiguration into a VHD</span></span>

<span data-ttu-id="f7dcb-144">Также можно настроить на компьютере извлечение конфигурации при начальной загрузке, добавив метаконфигурацию (см. раздел [Настройка локального диспетчера конфигурации [LCM]](../managing-nodes/metaConfig.md)) в VHD в качестве его файла `MetaConfig.mof`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-144">You can also configure a computer to pull a configuration at initial boot-up by injecting a metaconfiguration (see [Configuring the Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md)) into the VHD as its `MetaConfig.mof` file.</span></span> <span data-ttu-id="f7dcb-145">Если раздел реестра **DSCAutomationHostEnabled** имеет значение 2 (значение по умолчанию), DSC применяет к локальному диспетчеру конфигурации метаконфигурацию, определенную в `MetaConfig.mof` при первой загрузке компьютера.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-145">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the metaconfiguration defined by `MetaConfig.mof` to the LCM when the computer boots up for the first time.</span></span> <span data-ttu-id="f7dcb-146">Если в метаконфигурации указано, что локальный диспетчер конфигурации должен извлекать конфигурации с опрашивающего сервера, компьютер попытается извлечь конфигурации с этого сервера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-146">If the metaconfiguration specifies that the LCM should pull configurations from a pull server, the computer will attempt to pull a configuration from that pull server at initial boot-up.</span></span> <span data-ttu-id="f7dcb-147">Сведения о настройке опрашивающего сервера DSC см. в разделе [Настройка опрашивающего веб-сервера DSC](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-147">For information about setting up a DSC pull server, see [Setting up a DSC web pull server](../pull-server/pullServer.md).</span></span>

<span data-ttu-id="f7dcb-148">В этом примере используется конфигурация, описанная в предыдущем разделе (**SampleIISInstall**), и следующая метаконфигурация.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-148">For this example, we will use both the configuration described in the previous section (**SampleIISInstall**), and the following metaconfiguration:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientBootstrap
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
            ConfigurationNames = @('SampleIISInstall')
        }
    }
}
```

### <a name="to-inject-the-metaconfiguration-mof-document-on-the-vhd"></a><span data-ttu-id="f7dcb-149">Добавление документа MOF метаконфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="f7dcb-149">To inject the metaconfiguration MOF document on the VHD</span></span>

1. <span data-ttu-id="f7dcb-150">Подключите VHD, в который нужно добавить метаконфигурацию, вызвав командлет [Mount-VHD](/powershell/module/hyper-v/mount-vhd).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-150">Mount the VHD into which you want to inject the metaconfiguration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="f7dcb-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="f7dcb-151">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="f7dcb-152">[Настройте опрашиваемый веб-сервер DSC](../pull-server/pullServer.md) и сохраните конфигурацию **SampleIISInistall** в соответствующую папку.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-152">[Set up a DSC web pull server](../pull-server/pullServer.md), and save the **SampleIISInstall** configuration to the appropriate folder.</span></span>

1. <span data-ttu-id="f7dcb-153">На компьютере с PowerShell 5.0 или более поздней версией сохраните указанную выше метаконфигурацию (**PullClientBootstrap**) как файл сценария PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-153">On a computer running PowerShell 5.0 or later, save the above metaconfiguration (**PullClientBootstrap**) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="f7dcb-154">В консоли PowerShell перейдите в папку, где был сохранен PS1-файл.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-154">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="f7dcb-155">Выполните следующие команды PowerShell для компиляции документа MOF метаконфигурации (дополнительные сведения о компиляции конфигураций DSC см. в статье [Конфигурации DSC](../configurations/configurations.md)):</span><span class="sxs-lookup"><span data-stu-id="f7dcb-155">Run the following PowerShell commands to compile the metaconfiguration MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\PullClientBootstrap.ps1
   PullClientBootstrap
   ```

1. <span data-ttu-id="f7dcb-156">Будет создан файл `localhost.meta.mof` в новой папке с именем `PullClientBootstrap`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-156">This will create a `localhost.meta.mof` file in a new folder named `PullClientBootstrap`.</span></span> <span data-ttu-id="f7dcb-157">Переименуйте и переместите этот файл в нужное место на VHD как `MetaConfig.mof` при помощи командлета [Move-Item](/powershell/module/microsoft.powershell.management/move-item).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-157">Rename and move that file into the proper location on the VHD as `MetaConfig.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\PullClientBootstrap\localhost.meta.mof -Destination E:\Windows\System32\Configuration\MetaConfig.mof
   ```

1. <span data-ttu-id="f7dcb-158">Отключите VHD, вызвав командлет [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-158">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="f7dcb-159">Пример:</span><span class="sxs-lookup"><span data-stu-id="f7dcb-159">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="f7dcb-160">Создайте виртуальную машину с помощью VHD, на который установлен документ MOF DSC.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-160">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="f7dcb-161">После первоначальной загрузки и установки операционной системы DSC извлечет конфигурацию из опрашивающего сервера и будут установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-161">After initial boot-up and operating system installation, DSC will pull the configuration from the pull server, and IIS will be installed.</span></span> <span data-ttu-id="f7dcb-162">Это можно проверить, вызвав командлет [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-162">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="disable-dsc-at-boot-time"></a><span data-ttu-id="f7dcb-163">Отключение DSC при загрузке</span><span class="sxs-lookup"><span data-stu-id="f7dcb-163">Disable DSC at boot time</span></span>

<span data-ttu-id="f7dcb-164">По умолчанию для раздела реестра `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled`</span><span class="sxs-lookup"><span data-stu-id="f7dcb-164">By default, the value of the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled`</span></span>
<span data-ttu-id="f7dcb-165">задано значение 2, что позволяет запускать конфигурацию DSC, если компьютер находится в состоянии ожидания или в текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-165">key is set to 2, which allows a DSC configuration to run if the computer is in pending or current state.</span></span> <span data-ttu-id="f7dcb-166">Если запускать конфигурацию при начальной загрузке не следует, необходимо задать для этого раздела значение 0.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-166">If you do not want a configuration to run at initial boot-up, you need so set the value of this key to 0:</span></span>

1. <span data-ttu-id="f7dcb-167">Подключите VHD, вызвав командлет [Mount-VHD](/powershell/module/hyper-v/mount-vhd).</span><span class="sxs-lookup"><span data-stu-id="f7dcb-167">Mount the VHD by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="f7dcb-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="f7dcb-168">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="f7dcb-169">Загрузите подраздел реестра `HKLM\Software` с VHD, вызвав `reg load`.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-169">Load the registry `HKLM\Software` subkey from the VHD by calling `reg load`.</span></span>

   ```powershell
   reg load HKLM\Vhd E:\Windows\System32\Config\Software
   ```

1. <span data-ttu-id="f7dcb-170">В загруженном кусте замените значение `DSCAutomationHostEnabled` на 0.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-170">Change the value of `DSCAutomationHostEnabled` to 0 in the loaded hive.</span></span>

   ```powershell
   reg add "HKLM\Vhd\Software\Microsoft\Windows\CurrentVersion\Policies\System" /v DSCAutomationHostEnabled /t REG_DWORD /d 0 /f
   ```

1. <span data-ttu-id="f7dcb-171">Выгрузите реестр, выполнив следующие команды.</span><span class="sxs-lookup"><span data-stu-id="f7dcb-171">Unload the registry by running the following commands:</span></span>

   ```powershell
   reg unload HKLM\Vhd
   ```

## <a name="see-also"></a><span data-ttu-id="f7dcb-172">См. также</span><span class="sxs-lookup"><span data-stu-id="f7dcb-172">See Also</span></span>

[<span data-ttu-id="f7dcb-173">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="f7dcb-173">DSC Configurations</span></span>](../configurations/configurations.md)

[<span data-ttu-id="f7dcb-174">Раздел реестра DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="f7dcb-174">DSCAutomationHostEnabled registry key</span></span>](DSCAutomationHostEnabled.md)

[<span data-ttu-id="f7dcb-175">Настройка локального диспетчера конфигураций (LCM)</span><span class="sxs-lookup"><span data-stu-id="f7dcb-175">Configuring the Local Configuration Manager (LCM)</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="f7dcb-176">Настройка опрашивающего веб-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="f7dcb-176">Setting up a DSC web pull server</span></span>](../pull-server/pullServer.md)
