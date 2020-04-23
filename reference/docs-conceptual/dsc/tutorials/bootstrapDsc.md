---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Настройка виртуальных машин при начальной загрузке с помощью DSC
ms.openlocfilehash: f9634c330832e23fb2c6f08c5b299b55a5505ac9
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954611"
---
# <a name="configure-a-virtual-machines-at-initial-boot-up-by-using-dsc"></a><span data-ttu-id="db7e0-103">Настройка виртуальных машин при начальной загрузке с помощью DSC</span><span class="sxs-lookup"><span data-stu-id="db7e0-103">Configure a virtual machines at initial boot-up by using DSC</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db7e0-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="db7e0-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="requirements"></a><span data-ttu-id="db7e0-105">Требования</span><span class="sxs-lookup"><span data-stu-id="db7e0-105">Requirements</span></span>

> [!NOTE]
> <span data-ttu-id="db7e0-106">Раздел реестра **DSCAutomationHostEnabled**, описанный в этом разделе, недоступен в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="db7e0-106">The **DSCAutomationHostEnabled** registry key described in this topic is not available in PowerShell 4.0.</span></span>
> <span data-ttu-id="db7e0-107">Сведения о настройке новых виртуальных машин при начальной загрузке в PowerShell 4.0 см. в разделе [Требуется автоматически настроить машины с помощью DSC при начальной загрузке?](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/).</span><span class="sxs-lookup"><span data-stu-id="db7e0-107">For information on how to configure new virtual machines at initial boot-up in PowerShell 4.0, see [Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span></span>

<span data-ttu-id="db7e0-108">Для выполнения этих примеров требуется следующее.</span><span class="sxs-lookup"><span data-stu-id="db7e0-108">To run these examples, you will need:</span></span>

- <span data-ttu-id="db7e0-109">Загрузочный VHD.</span><span class="sxs-lookup"><span data-stu-id="db7e0-109">A bootable VHD to work with.</span></span> <span data-ttu-id="db7e0-110">ISO-файл с пробной версией Windows Server 2016 можно скачать в центре [TechNet Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="db7e0-110">You can download an ISO with an evaluation copy of Windows Server 2016 at [TechNet Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016).</span></span>
  <span data-ttu-id="db7e0-111">Инструкции по созданию VHD из ISO-образа см. в разделе [Создание загрузочных виртуальных жестких дисков](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="db7e0-111">You can find instructions on how to create a VHD from an ISO image at [Creating Bootable Virtual Hard Disks](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span></span>
- <span data-ttu-id="db7e0-112">Компьютер с включенным Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="db7e0-112">A host computer that has Hyper-V enabled.</span></span> <span data-ttu-id="db7e0-113">Дополнительные сведения см. в статье [Обзор Hyper-V](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="db7e0-113">For information, see [Hyper-V overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span></span>

  <span data-ttu-id="db7e0-114">С помощью DSC можно автоматизировать установку и настройку программного обеспечения для компьютера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="db7e0-114">By using DSC, you can automate software installation and configuration for a computer at initial boot-up.</span></span>
  <span data-ttu-id="db7e0-115">Для этого необходимо добавить документ MOF конфигурации или метаконфигурацию на загрузочный носитель (например, VHD), чтобы они выполнялись при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="db7e0-115">You do this by either injecting a configuration MOF document or a metaconfiguration into bootable media (such as a VHD) so that they are run during the initial boot-up process.</span></span>
  <span data-ttu-id="db7e0-116">Такое поведение контролируется [разделом реестра DSCAutomationHostEnabled](DSCAutomationHostEnabled.md) в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-116">This behavior is specified by the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key under `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span></span>
  <span data-ttu-id="db7e0-117">По умолчанию значение этого раздела — 2, что позволяет DSC запускаться во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="db7e0-117">By default, the value of this key is 2, which allows DSC to run at boot time.</span></span>

  <span data-ttu-id="db7e0-118">Если запускать DSC во время загрузки не следует, задайте для [раздела реестра DSCAutomationHostEnabled](DSCAutomationHostEnabled.md) значение 0.</span><span class="sxs-lookup"><span data-stu-id="db7e0-118">If you do not want DSC to run at boot time, set the value of the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key to 0.</span></span>

- <span data-ttu-id="db7e0-119">Добавление документа MOF конфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="db7e0-119">Inject a configuration MOF document into a VHD</span></span>
- <span data-ttu-id="db7e0-120">Добавление метаконфигурации DSC в VHD</span><span class="sxs-lookup"><span data-stu-id="db7e0-120">Inject a DSC metaconfiguration into a VHD</span></span>
- <span data-ttu-id="db7e0-121">Отключение DSC при загрузке</span><span class="sxs-lookup"><span data-stu-id="db7e0-121">Disable DSC at boot time</span></span>

> [!NOTE]
> <span data-ttu-id="db7e0-122">На компьютер можно одновременно добавить `Pending.mof` и `MetaConfig.mof`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-122">You can inject both `Pending.mof` and `MetaConfig.mof` into a computer at the same time.</span></span>
> <span data-ttu-id="db7e0-123">Если присутствуют оба файла, более высокий приоритет имеют параметры, указанные в `MetaConfig.mof`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-123">If both files are present, the settings specified in `MetaConfig.mof` take precedence.</span></span>

## <a name="inject-a-configuration-mof-document-into-a-vhd"></a><span data-ttu-id="db7e0-124">Добавление документа MOF конфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="db7e0-124">Inject a configuration MOF document into a VHD</span></span>

<span data-ttu-id="db7e0-125">Для применения конфигурации при начальной загрузке добавьте скомпилированный документ MOF конфигурации в VHD в качестве его файла `Pending.mof`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-125">To enact a configuration at initial boot-up, you can inject a compiled configuration MOF document into the VHD as its `Pending.mof` file.</span></span>
<span data-ttu-id="db7e0-126">Если раздел реестра **DSCAutomationHostEnabled** имеет значение 2 (значение по умолчанию), DSC применяет конфигурацию, определенную в `Pending.mof`, при первой загрузке компьютера.</span><span class="sxs-lookup"><span data-stu-id="db7e0-126">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the configuration defined by `Pending.mof` when the computer boots up for the first time.</span></span>

<span data-ttu-id="db7e0-127">В этом примере используется следующая конфигурация, которая устанавливает службы IIS на новом компьютере.</span><span class="sxs-lookup"><span data-stu-id="db7e0-127">For this example, we will use the following configuration, which will install IIS on the new computer:</span></span>

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

### <a name="to-inject-the-configuration-mof-document-on-the-vhd"></a><span data-ttu-id="db7e0-128">Добавление документа MOF конфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="db7e0-128">To inject the configuration MOF document on the VHD</span></span>

1. <span data-ttu-id="db7e0-129">Подключите VHD, в который нужно добавить конфигурацию, вызвав командлет [Mount-VHD](/powershell/module/hyper-v/mount-vhd).</span><span class="sxs-lookup"><span data-stu-id="db7e0-129">Mount the VHD into which you want to inject the configuration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="db7e0-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="db7e0-130">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

2. <span data-ttu-id="db7e0-131">На компьютере с PowerShell 5.0 или более поздней версией сохраните указанную выше конфигурацию (**SampleIISInstall**) как файл сценария PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="db7e0-131">On a computer running PowerShell 5.0 or later, save the above configuration (**SampleIISInstall**) as a PowerShell script (.ps1) file.</span></span>

3. <span data-ttu-id="db7e0-132">В консоли PowerShell перейдите в папку, где был сохранен PS1-файл.</span><span class="sxs-lookup"><span data-stu-id="db7e0-132">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

4. <span data-ttu-id="db7e0-133">Выполните следующие команды PowerShell для компиляции документа MOF (дополнительные сведения о компиляции конфигураций DSC см. в разделе [Конфигурации DSC](../configurations/configurations.md)).</span><span class="sxs-lookup"><span data-stu-id="db7e0-133">Run the following PowerShell commands to compile the MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\SampleIISInstall.ps1
   SampleIISInstall
   ```

5. <span data-ttu-id="db7e0-134">Будет создан файл `localhost.mof` в новой папке с именем `SampleIISInstall`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-134">This will create a `localhost.mof` file in a new folder named `SampleIISInstall`.</span></span>
   <span data-ttu-id="db7e0-135">Переименуйте и переместите этот файл в нужное место на VHD как `Pending.mof` при помощи командлета [Move-Item](/powershell/module/microsoft.powershell.management/move-item).</span><span class="sxs-lookup"><span data-stu-id="db7e0-135">Rename and move that file into the proper location on the VHD as `Pending.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span> <span data-ttu-id="db7e0-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="db7e0-136">For example:</span></span>

   ```powershell
       Move-Item -Path C:\DSCTest\SampleIISInstall\localhost.mof -Destination E:\Windows\System32\Configuration\Pending.mof
   ```

6. <span data-ttu-id="db7e0-137">Отключите VHD, вызвав командлет [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd).</span><span class="sxs-lookup"><span data-stu-id="db7e0-137">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span> <span data-ttu-id="db7e0-138">Пример:</span><span class="sxs-lookup"><span data-stu-id="db7e0-138">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

7. <span data-ttu-id="db7e0-139">Создайте виртуальную машину с помощью VHD, на который установлен документ MOF DSC.</span><span class="sxs-lookup"><span data-stu-id="db7e0-139">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="db7e0-140">После первоначальной загрузки и установки операционной системы будут установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="db7e0-140">After initial boot-up and operating system installation, IIS will be installed.</span></span>
<span data-ttu-id="db7e0-141">Это можно проверить, вызвав командлет [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature).</span><span class="sxs-lookup"><span data-stu-id="db7e0-141">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="inject-a-dsc-metaconfiguration-into-a-vhd"></a><span data-ttu-id="db7e0-142">Добавление метаконфигурации DSC в VHD</span><span class="sxs-lookup"><span data-stu-id="db7e0-142">Inject a DSC metaconfiguration into a VHD</span></span>

<span data-ttu-id="db7e0-143">Также можно настроить на компьютере извлечение конфигурации при начальной загрузке, добавив метаконфигурацию (см. раздел [Настройка локального диспетчера конфигурации [LCM]](../managing-nodes/metaConfig.md)) в VHD в качестве его файла `MetaConfig.mof`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-143">You can also configure a computer to pull a configuration at initial boot-up by injecting a metaconfiguration (see [Configuring the Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md)) into the VHD as its `MetaConfig.mof` file.</span></span>
<span data-ttu-id="db7e0-144">Если раздел реестра **DSCAutomationHostEnabled** имеет значение 2 (значение по умолчанию), DSC применяет к локальному диспетчеру конфигурации метаконфигурацию, определенную в `MetaConfig.mof` при первой загрузке компьютера.</span><span class="sxs-lookup"><span data-stu-id="db7e0-144">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value),  DSC will apply the metaconfiguration defined by `MetaConfig.mof` to the LCM when the computer boots up for the first time.</span></span>
<span data-ttu-id="db7e0-145">Если в метаконфигурации указано, что локальный диспетчер конфигурации должен извлекать конфигурации с опрашивающего сервера, компьютер попытается извлечь конфигурации с этого сервера при начальной загрузке.</span><span class="sxs-lookup"><span data-stu-id="db7e0-145">If the metaconfiguration specifies that the LCM should pull configurations from a pull server, the computer will attempt to pull a configuration from that pull server at initial boot-up.</span></span>
<span data-ttu-id="db7e0-146">Сведения о настройке опрашивающего сервера DSC см. в разделе [Настройка опрашивающего веб-сервера DSC](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="db7e0-146">For information about setting up a DSC pull server, see [Setting up a DSC web pull server](../pull-server/pullServer.md).</span></span>

<span data-ttu-id="db7e0-147">В этом примере используется конфигурация, описанная в предыдущем разделе (**SampleIISInstall**), и следующая метаконфигурация.</span><span class="sxs-lookup"><span data-stu-id="db7e0-147">For this example, we will use both the configuration described in the previous section (**SampleIISInstall**), and the following metaconfiguration:</span></span>

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

### <a name="to-inject-the-metaconfiguration-mof-document-on-the-vhd"></a><span data-ttu-id="db7e0-148">Добавление документа MOF метаконфигурации в VHD</span><span class="sxs-lookup"><span data-stu-id="db7e0-148">To inject the metaconfiguration MOF document on the VHD</span></span>

1. <span data-ttu-id="db7e0-149">Подключите VHD, в который нужно добавить метаконфигурацию, вызвав командлет [Mount-VHD](/powershell/module/hyper-v/mount-vhd).</span><span class="sxs-lookup"><span data-stu-id="db7e0-149">Mount the VHD into which you want to inject the metaconfiguration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="db7e0-150">Пример:</span><span class="sxs-lookup"><span data-stu-id="db7e0-150">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

2. <span data-ttu-id="db7e0-151">[Настройте опрашиваемый веб-сервер DSC](../pull-server/pullServer.md) и сохраните конфигурацию **SampleIISInistall** в соответствующую папку.</span><span class="sxs-lookup"><span data-stu-id="db7e0-151">[Set up a DSC web pull server](../pull-server/pullServer.md), and save the **SampleIISInstall** configuration to the appropriate folder.</span></span>

3. <span data-ttu-id="db7e0-152">На компьютере с PowerShell 5.0 или более поздней версией сохраните указанную выше метаконфигурацию (**PullClientBootstrap**) как файл сценария PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="db7e0-152">On a computer running PowerShell 5.0 or later, save the above metaconfiguration (**PullClientBootstrap**) as a PowerShell script (.ps1) file.</span></span>

4. <span data-ttu-id="db7e0-153">В консоли PowerShell перейдите в папку, где был сохранен PS1-файл.</span><span class="sxs-lookup"><span data-stu-id="db7e0-153">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

5. <span data-ttu-id="db7e0-154">Выполните следующие команды PowerShell для компиляции документа MOF метаконфигурации (дополнительные сведения о компиляции конфигураций DSC см. в разделе [Конфигурации DSC](../configurations/configurations.md)).</span><span class="sxs-lookup"><span data-stu-id="db7e0-154">Run the following PowerShell commands to compile the  metaconfiguration MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\PullClientBootstrap.ps1
   PullClientBootstrap
   ```

6. <span data-ttu-id="db7e0-155">Будет создан файл `localhost.meta.mof` в новой папке с именем `PullClientBootstrap`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-155">This will create a `localhost.meta.mof` file in a new folder named `PullClientBootstrap`.</span></span>
   <span data-ttu-id="db7e0-156">Переименуйте и переместите этот файл в нужное место на VHD как `MetaConfig.mof` при помощи командлета [Move-Item](/powershell/module/microsoft.powershell.management/move-item).</span><span class="sxs-lookup"><span data-stu-id="db7e0-156">Rename and move that file into the proper location on the VHD as `MetaConfig.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\PullClientBootstrap\localhost.meta.mof -Destination E:\Windows\System32\Configuration\MetaConfig.mof
   ```

7. <span data-ttu-id="db7e0-157">Отключите VHD, вызвав командлет [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd).</span><span class="sxs-lookup"><span data-stu-id="db7e0-157">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span> <span data-ttu-id="db7e0-158">Пример:</span><span class="sxs-lookup"><span data-stu-id="db7e0-158">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

8. <span data-ttu-id="db7e0-159">Создайте виртуальную машину с помощью VHD, на который установлен документ MOF DSC.</span><span class="sxs-lookup"><span data-stu-id="db7e0-159">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="db7e0-160">После первоначальной загрузки и установки операционной системы DSC извлечет конфигурацию из опрашивающего сервера и будут установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="db7e0-160">After initial boot-up and operating system installation, DSC will pull the configuration from the pull server, and IIS will be installed.</span></span>
<span data-ttu-id="db7e0-161">Это можно проверить, вызвав командлет [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature).</span><span class="sxs-lookup"><span data-stu-id="db7e0-161">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="disable-dsc-at-boot-time"></a><span data-ttu-id="db7e0-162">Отключение DSC при загрузке</span><span class="sxs-lookup"><span data-stu-id="db7e0-162">Disable DSC at boot time</span></span>

<span data-ttu-id="db7e0-163">По умолчанию раздел `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled` имеет значение 2, что позволяет запускать конфигурацию DSC, если компьютер находится в состоянии ожидания или в текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="db7e0-163">By default, the value of the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled` key is set to 2, which allows a DSC configuration to run if the computer is in pending or current state.</span></span> <span data-ttu-id="db7e0-164">Если запускать конфигурацию при начальной загрузке не следует, необходимо задать для этого раздела значение 0.</span><span class="sxs-lookup"><span data-stu-id="db7e0-164">If you do not want a configuration to run at initial boot-up, you need so set the value of this key to 0:</span></span>

1. <span data-ttu-id="db7e0-165">Подключите VHD, вызвав командлет [Mount-VHD](/powershell/module/hyper-v/mount-vhd).</span><span class="sxs-lookup"><span data-stu-id="db7e0-165">Mount the VHD by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="db7e0-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="db7e0-166">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

2. <span data-ttu-id="db7e0-167">Загрузите подраздел реестра `HKLM\Software` с VHD, вызвав `reg load`.</span><span class="sxs-lookup"><span data-stu-id="db7e0-167">Load the registry `HKLM\Software` subkey from the VHD by calling `reg load`.</span></span>

   ```powershell
   reg load HKLM\Vhd E:\Windows\System32\Config\Software`
   ```

3. <span data-ttu-id="db7e0-168">Перейдите в раздел `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` с помощью поставщика реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db7e0-168">Navigate to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` by using the PowerShell Registry provider.</span></span>

   ```powershell
   Set-Location HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\System`
   ```

4. <span data-ttu-id="db7e0-169">Измените значение `DSCAutomationHostEnabled` на 0.</span><span class="sxs-lookup"><span data-stu-id="db7e0-169">Change the value of `DSCAutomationHostEnabled` to 0.</span></span>

   ```powershell
   Set-ItemProperty -Path . -Name DSCAutomationHostEnabled -Value 0
   ```

5. <span data-ttu-id="db7e0-170">Выгрузите реестр, выполнив следующие команды.</span><span class="sxs-lookup"><span data-stu-id="db7e0-170">Unload the registry by running the following commands:</span></span>

   ```powershell
   [gc]::Collect()
   reg unload HKLM\Vhd
   ```

## <a name="see-also"></a><span data-ttu-id="db7e0-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="db7e0-171">See Also</span></span>

[<span data-ttu-id="db7e0-172">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="db7e0-172">DSC Configurations</span></span>](../configurations/configurations.md)

[<span data-ttu-id="db7e0-173">Раздел реестра DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="db7e0-173">DSCAutomationHostEnabled registry key</span></span>](DSCAutomationHostEnabled.md)

[<span data-ttu-id="db7e0-174">Настройка локального диспетчера конфигураций (LCM)</span><span class="sxs-lookup"><span data-stu-id="db7e0-174">Configuring the Local Configuration Manager (LCM)</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="db7e0-175">Настройка опрашивающего веб-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="db7e0-175">Setting up a DSC web pull server</span></span>](../pull-server/pullServer.md)
