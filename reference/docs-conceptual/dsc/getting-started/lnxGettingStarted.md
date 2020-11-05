---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Начало работы с настройкой требуемого состояния (DSC) для Linux
description: В этом разделе объясняется, как приступить к работе с настройкой требуемого состояния PowerShell (DSC) для Linux.
ms.openlocfilehash: 826707654a297306c39d4dfcfd3941f56b7cf91d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651113"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="4af03-104">Начало работы с настройкой требуемого состояния (DSC) для Linux</span><span class="sxs-lookup"><span data-stu-id="4af03-104">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="4af03-105">В этом разделе объясняется, как приступить к работе с настройкой требуемого состояния PowerShell (DSC) для Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-105">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span>
<span data-ttu-id="4af03-106">Общие сведения о службе настройки требуемого состояния см. в разделе [Начало работы со службой настройки требуемого состояния Windows PowerShell](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="4af03-106">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="4af03-107">Поддерживаемые версии операционной системы Linux</span><span class="sxs-lookup"><span data-stu-id="4af03-107">Supported Linux operation system versions</span></span>

<span data-ttu-id="4af03-108">DSC для Linux поддерживает следующие версии операционной системы Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-108">The following Linux operating system versions are supported by DSC for Linux.</span></span>

- <span data-ttu-id="4af03-109">CentOS 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="4af03-109">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="4af03-110">Debian GNU/Linux 6, 7 и 8 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="4af03-110">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="4af03-111">Oracle Linux 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="4af03-111">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="4af03-112">Red Hat Enterprise Linux Server 5, 6 и 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="4af03-112">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="4af03-113">SUSE Linux Enterprise Server 10, 11 и 12 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="4af03-113">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="4af03-114">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="4af03-114">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span></span>

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="4af03-115">Установка DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="4af03-115">Installing DSC for Linux</span></span>

<span data-ttu-id="4af03-116">Перед установкой DSC для Linux необходимо установить [открытую инфраструктуру управления (OMI)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="4af03-116">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="4af03-117">Установка OMI</span><span class="sxs-lookup"><span data-stu-id="4af03-117">Installing OMI</span></span>

<span data-ttu-id="4af03-118">Настройка требуемого состояния для Linux требует наличия CIM-сервера открытой инфраструктуры управления (OMI) версии 1.0.8.1 и выше.</span><span class="sxs-lookup"><span data-stu-id="4af03-118">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="4af03-119">OMI можно скачать на сайте Open Group: [Открытая инфраструктура управления (OMI)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="4af03-119">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="4af03-120">Чтобы установить OMI, установите пакет, соответствующий вашей системе Linux (RPM или DEB), а также версии OpenSSL (ssl_098 или ssl_100) и архитектуре (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="4af03-120">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="4af03-121">Пакеты RPM подходят для CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-121">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="4af03-122">Пакеты DEB подходят для Debian GNU/Linux и Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="4af03-122">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="4af03-123">Пакеты ssl_098 подходят для компьютеров с установленным OpenSSL 0.9.8, а пакеты ssl_100 — для компьютеров с установленным OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="4af03-123">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="4af03-124">Чтобы определить установленную версию OpenSSL, выполните команду `openssl version`.</span><span class="sxs-lookup"><span data-stu-id="4af03-124">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="4af03-125">Выполните указанную ниже команду для установки OMI в системе CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="4af03-125">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="4af03-126">Установка DSC</span><span class="sxs-lookup"><span data-stu-id="4af03-126">Installing DSC</span></span>

<span data-ttu-id="4af03-127">DSC для Linux можно скачать из репозитория [PowerShell-DSC-for-Linux](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span><span class="sxs-lookup"><span data-stu-id="4af03-127">DSC for Linux is available for download from the [PowerShell-DSC-for-Linux](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294) repository in the repository.</span></span>

<span data-ttu-id="4af03-128">Чтобы установить DSC, установите пакет, соответствующий вашей системе Linux (RPM или DEB), а также версии OpenSSL (ssl_098 или ssl_100) и архитектуре (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="4af03-128">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="4af03-129">Пакеты RPM подходят для CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-129">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="4af03-130">Пакеты DEB подходят для Debian GNU/Linux и Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="4af03-130">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="4af03-131">Пакеты ssl_098 подходят для компьютеров с установленным OpenSSL 0.9.8, а пакеты ssl_100 — для компьютеров с установленным OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="4af03-131">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="4af03-132">Чтобы определить установленную версию OpenSSL, выполните команду openssl.</span><span class="sxs-lookup"><span data-stu-id="4af03-132">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="4af03-133">Выполните указанную ниже команду для установки DSC в системе CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="4af03-133">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="4af03-134">Использование DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="4af03-134">Using DSC for Linux</span></span>

<span data-ttu-id="4af03-135">В следующих разделах описывается создание и запуск конфигураций DSC на компьютерах Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-135">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="4af03-136">Создание MOF-документа конфигурации</span><span class="sxs-lookup"><span data-stu-id="4af03-136">Creating a configuration MOF document</span></span>

<span data-ttu-id="4af03-137">На компьютерах Linux (как и на компьютерах Windows) для создания конфигурации используется ключевое слово конфигурации Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af03-137">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="4af03-138">Следующие шаги описывают создание документа конфигурации для компьютера Linux с использованием Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af03-138">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="4af03-139">Импортируйте модуль nx.</span><span class="sxs-lookup"><span data-stu-id="4af03-139">Import the nx module.</span></span> <span data-ttu-id="4af03-140">Модуль nx для Windows PowerShell содержит схему для встроенных ресурсов DSC в Linux, поэтому он должен быть установлен на локальном компьютере и импортирован в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="4af03-140">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="4af03-141">Чтобы установить модуль nx, скопируйте каталог модуля nx в `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` или в `$PSHOME\Modules`.</span><span class="sxs-lookup"><span data-stu-id="4af03-141">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="4af03-142">Модуль nx включается в пакет установки DSC для Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-142">The nx module is included in the DSC for Linux installation package.</span></span> <span data-ttu-id="4af03-143">Чтобы импортировать модуль nx в конфигурацию, выполните команду `Import-DSCResource`:</span><span class="sxs-lookup"><span data-stu-id="4af03-143">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="4af03-144">Определите конфигурацию и создайте документ конфигурации:</span><span class="sxs-lookup"><span data-stu-id="4af03-144">Define a configuration and generate the configuration document:</span></span>

   ```powershell
   Configuration ExampleConfiguration
   {
        Import-DscResource -Module nx

        Node  "linuxhost.contoso.com"
        {
            nxFile ExampleFile
            {
                DestinationPath = "/tmp/example"
                Contents = "hello world `n"
                Ensure = "Present"
                Type = "File"
            }
        }
   }

   ExampleConfiguration -OutputPath:"C:\temp"
   ```

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="4af03-145">Передача конфигурации на компьютер Linux</span><span class="sxs-lookup"><span data-stu-id="4af03-145">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="4af03-146">Документы конфигурации (MOF-файлы) можно принудительно отправить на компьютер Linux с помощью командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="4af03-146">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="4af03-147">Чтобы выполнить этот командлет, как и командлеты [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) или [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), удаленно на компьютере Linux, необходимо использовать CIMSession.</span><span class="sxs-lookup"><span data-stu-id="4af03-147">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="4af03-148">Для создания **CIMSession** на компьютере Linux служит командлет [New-CimSession](/powershell/module/CimCmdlets/New-CimSession).</span><span class="sxs-lookup"><span data-stu-id="4af03-148">The [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet is used to create a **CIMSession** to the Linux computer.</span></span>

<span data-ttu-id="4af03-149">Создание CIMSession в DSC для Linux демонстрируется в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4af03-149">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

```powershell
$Node = "ostc-dsc-01"
$Credential = Get-Credential -UserName "root" -Message "Enter Password:"

#Ignore SSL certificate validation
#$opt = New-CimSessionOption -UseSsl $true -SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true

#Options for a trusted SSL certificate
$opt = New-CimSessionOption -UseSsl $true
$Sess=New-CimSession -Credential $credential -ComputerName $Node -Port 5986 -Authentication basic -SessionOption $opt -OperationTimeoutSec 90
```

> [!NOTE]
> <span data-ttu-id="4af03-150">В режиме принудительной передачи необходимо указывать учетные данные привилегированного пользователя на компьютере Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-150">For "Push" mode, the user credential must be the root user on the Linux computer.</span></span> <span data-ttu-id="4af03-151">DSC для Linux поддерживает только SSL/TLS-подключения, поэтому необходимо использовать командлет `New-CimSession` с параметром –UseSSL, имеющим значение $true.</span><span class="sxs-lookup"><span data-stu-id="4af03-151">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span> <span data-ttu-id="4af03-152">SSL-сертификат, используемый OMI (DSC), указан в файле `/etc/opt/omi/conf/omiserver.conf` со свойствами pemfile и keyfile.</span><span class="sxs-lookup"><span data-stu-id="4af03-152">The SSL certificate used by OMI (for DSC) is specified in the file: `/etc/opt/omi/conf/omiserver.conf` with the properties: pemfile and keyfile.</span></span> <span data-ttu-id="4af03-153">Если компьютер Windows, на котором выполняется командлет [New-CimSession](/powershell/module/CimCmdlets/New-CimSession), не признает этот сертификат как надежный, проверку сертификата можно пропустить, используя параметры CIMSession: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span><span class="sxs-lookup"><span data-stu-id="4af03-153">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span></span>

<span data-ttu-id="4af03-154">Для принудительной отправки конфигурации DSC на узел Linux используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4af03-154">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession $Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="4af03-155">Распространение конфигурации через опрашивающий сервер</span><span class="sxs-lookup"><span data-stu-id="4af03-155">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="4af03-156">Конфигурации можно распространять на компьютер Linux через опрашивающий сервер, как и в случае компьютеров с Windows.</span><span class="sxs-lookup"><span data-stu-id="4af03-156">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="4af03-157">Рекомендации по работе с опрашивающим сервером см. в статье [Опрашивающие серверы настройки требуемого состояния Windows PowerShell](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="4af03-157">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](../pull-server/pullServer.md).</span></span> <span data-ttu-id="4af03-158">Дополнительные сведения и ограничения, связанные с использованием компьютеров Linux с опрашивающим сервером, см. в заметках о выпуске настройки требуемого состояния для Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-158">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="4af03-159">Локальная работа с конфигурациями</span><span class="sxs-lookup"><span data-stu-id="4af03-159">Working with configurations locally</span></span>

<span data-ttu-id="4af03-160">DSC для Linux включает сценарии работы с конфигурацией на локальном компьютере Linux.</span><span class="sxs-lookup"><span data-stu-id="4af03-160">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="4af03-161">Эти сценарии расположены в `/opt/microsoft/dsc/Scripts` и включают следующее:</span><span class="sxs-lookup"><span data-stu-id="4af03-161">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="4af03-162">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="4af03-162">GetDscConfiguration.py</span></span>

  <span data-ttu-id="4af03-163">Возвращает текущую конфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4af03-163">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="4af03-164">Аналог командлета `Get-DscConfiguration` в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af03-164">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

  `# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="4af03-165">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="4af03-165">GetDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="4af03-166">Возвращает текущую метаконфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4af03-166">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="4af03-167">Аналог командлета [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="4af03-167">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

  `# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="4af03-168">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="4af03-168">InstallModule.py</span></span>

  <span data-ttu-id="4af03-169">Устанавливает пользовательский модуль ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="4af03-169">Installs a custom DSC resource module.</span></span> <span data-ttu-id="4af03-170">Необходим путь к ZIP-файлу, содержащему библиотеку общих объектов модуля и MOF-файлы схемы.</span><span class="sxs-lookup"><span data-stu-id="4af03-170">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

 `# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="4af03-171">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="4af03-171">RemoveModule.py</span></span>

  <span data-ttu-id="4af03-172">Удаляет пользовательский модуль ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="4af03-172">Removes a custom DSC resource module.</span></span> <span data-ttu-id="4af03-173">Требуется имя модуля, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="4af03-173">Requires the name of the module to remove.</span></span>

  `# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="4af03-174">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="4af03-174">StartDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="4af03-175">Применяет MOF-файл конфигурации к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4af03-175">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="4af03-176">Аналог командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="4af03-176">Similar to the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="4af03-177">Требуется путь к соответствующему MOF-файлу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4af03-177">Requires the path to the configuration MOF to apply.</span></span>

  `# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="4af03-178">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="4af03-178">SetDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="4af03-179">Применяет MOF-файл метаконфигурации к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4af03-179">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="4af03-180">Аналог командлета [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="4af03-180">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="4af03-181">Требуется путь к соответствующему MOF-файлу метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="4af03-181">Requires the path to the Meta Configuration MOF to apply.</span></span>

  `# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="4af03-182">Настройка требуемого состояния Windows PowerShell для файлов журнала Linux</span><span class="sxs-lookup"><span data-stu-id="4af03-182">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="4af03-183">Для сообщений DSC для Linux формируются следующие файлы журналов:</span><span class="sxs-lookup"><span data-stu-id="4af03-183">The following log files are generated for DSC for Linux messages.</span></span>

|     <span data-ttu-id="4af03-184">Файл журнала</span><span class="sxs-lookup"><span data-stu-id="4af03-184">Log file</span></span>      |     <span data-ttu-id="4af03-185">Каталог</span><span class="sxs-lookup"><span data-stu-id="4af03-185">Directory</span></span>      |                                               <span data-ttu-id="4af03-186">Описание</span><span class="sxs-lookup"><span data-stu-id="4af03-186">Description</span></span>                                                |
| ----------------- | ------------------ | -------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="4af03-187">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="4af03-187">**omiserver.log**</span></span> | `/var/opt/omi/log` | <span data-ttu-id="4af03-188">Сообщения, относящиеся к работе сервера OMI CIM.</span><span class="sxs-lookup"><span data-stu-id="4af03-188">Messages relating to the operation of the OMI CIM server.</span></span>                                                |
| <span data-ttu-id="4af03-189">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="4af03-189">**dsc.log**</span></span>       | `/var/opt/omi/log` | <span data-ttu-id="4af03-190">Сообщения, относящиеся к работе локального диспетчера конфигураций (LCM) и операциям с ресурсами DSC.</span><span class="sxs-lookup"><span data-stu-id="4af03-190">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span> |
