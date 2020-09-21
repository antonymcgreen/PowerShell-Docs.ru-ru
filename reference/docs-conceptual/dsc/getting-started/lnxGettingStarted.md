---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Начало работы с настройкой требуемого состояния (DSC) для Linux
ms.openlocfilehash: 64657dda04fa2df97fa2ad7c7a5c2d15b66a270a
ms.sourcegitcommit: 4bb44f183dcbfa8dced57f075812e02d3b45fd70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86301341"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="c3315-103">Начало работы с настройкой требуемого состояния (DSC) для Linux</span><span class="sxs-lookup"><span data-stu-id="c3315-103">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="c3315-104">В этом разделе объясняется, как приступить к работе с настройкой требуемого состояния PowerShell (DSC) для Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span> <span data-ttu-id="c3315-105">Общие сведения о службе настройки требуемого состояния см. в разделе [Начало работы со службой настройки требуемого состояния Windows PowerShell](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="c3315-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="c3315-106">Поддерживаемые версии операционной системы Linux</span><span class="sxs-lookup"><span data-stu-id="c3315-106">Supported Linux operation system versions</span></span>

<span data-ttu-id="c3315-107">DSC для Linux поддерживает следующие версии операционной системы Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-107">The following Linux operating system versions are supported by DSC for Linux.</span></span>

- <span data-ttu-id="c3315-108">CentOS 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="c3315-108">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="c3315-109">Debian GNU/Linux 6, 7 и 8 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="c3315-109">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="c3315-110">Oracle Linux 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="c3315-110">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="c3315-111">Red Hat Enterprise Linux Server 5, 6 и 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="c3315-111">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="c3315-112">SUSE Linux Enterprise Server 10, 11 и 12 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="c3315-112">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="c3315-113">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="c3315-113">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS (x86/x64)</span></span>

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="c3315-114">Установка DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="c3315-114">Installing DSC for Linux</span></span>

<span data-ttu-id="c3315-115">Перед установкой DSC для Linux необходимо установить [открытую инфраструктуру управления (OMI)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="c3315-115">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="c3315-116">Установка OMI</span><span class="sxs-lookup"><span data-stu-id="c3315-116">Installing OMI</span></span>

<span data-ttu-id="c3315-117">Настройка требуемого состояния для Linux требует наличия CIM-сервера открытой инфраструктуры управления (OMI) версии 1.0.8.1 и выше.</span><span class="sxs-lookup"><span data-stu-id="c3315-117">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="c3315-118">OMI можно скачать на сайте Open Group: [Открытая инфраструктура управления (OMI)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="c3315-118">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="c3315-119">Чтобы установить OMI, установите пакет, соответствующий вашей системе Linux (RPM или DEB), а также версии OpenSSL (ssl_098 или ssl_100) и архитектуре (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="c3315-119">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="c3315-120">Пакеты RPM подходят для CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-120">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="c3315-121">Пакеты DEB подходят для Debian GNU/Linux и Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="c3315-121">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="c3315-122">Пакеты ssl_098 подходят для компьютеров с установленным OpenSSL 0.9.8, а пакеты ssl_100 — для компьютеров с установленным OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="c3315-122">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="c3315-123">Чтобы определить установленную версию OpenSSL, выполните команду `openssl version`.</span><span class="sxs-lookup"><span data-stu-id="c3315-123">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="c3315-124">Выполните указанную ниже команду для установки OMI в системе CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="c3315-124">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="c3315-125">Установка DSC</span><span class="sxs-lookup"><span data-stu-id="c3315-125">Installing DSC</span></span>

<span data-ttu-id="c3315-126">DSC для Linux можно скачать [здесь](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span><span class="sxs-lookup"><span data-stu-id="c3315-126">DSC for Linux is available for download [here](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span></span>

<span data-ttu-id="c3315-127">Чтобы установить DSC, установите пакет, соответствующий вашей системе Linux (RPM или DEB), а также версии OpenSSL (ssl_098 или ssl_100) и архитектуре (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="c3315-127">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="c3315-128">Пакеты RPM подходят для CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-128">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="c3315-129">Пакеты DEB подходят для Debian GNU/Linux и Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="c3315-129">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="c3315-130">Пакеты ssl_098 подходят для компьютеров с установленным OpenSSL 0.9.8, а пакеты ssl_100 — для компьютеров с установленным OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="c3315-130">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="c3315-131">Чтобы определить установленную версию OpenSSL, выполните команду openssl.</span><span class="sxs-lookup"><span data-stu-id="c3315-131">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="c3315-132">Выполните указанную ниже команду для установки DSC в системе CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="c3315-132">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="c3315-133">Использование DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="c3315-133">Using DSC for Linux</span></span>

<span data-ttu-id="c3315-134">В следующих разделах описывается создание и запуск конфигураций DSC на компьютерах Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-134">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="c3315-135">Создание MOF-документа конфигурации</span><span class="sxs-lookup"><span data-stu-id="c3315-135">Creating a configuration MOF document</span></span>

<span data-ttu-id="c3315-136">На компьютерах Linux (как и на компьютерах Windows) для создания конфигурации используется ключевое слово конфигурации Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3315-136">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="c3315-137">Следующие шаги описывают создание документа конфигурации для компьютера Linux с использованием Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3315-137">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="c3315-138">Импортируйте модуль nx.</span><span class="sxs-lookup"><span data-stu-id="c3315-138">Import the nx module.</span></span> <span data-ttu-id="c3315-139">Модуль nx для Windows PowerShell содержит схему для встроенных ресурсов DSC в Linux, поэтому он должен быть установлен на локальном компьютере и импортирован в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="c3315-139">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="c3315-140">Чтобы установить модуль nx, скопируйте каталог модуля nx в `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` или в `$PSHOME\Modules`.</span><span class="sxs-lookup"><span data-stu-id="c3315-140">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="c3315-141">Модуль nx включается в пакет установки DSC для Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-141">The nx module is included in the DSC for Linux installation package.</span></span> <span data-ttu-id="c3315-142">Чтобы импортировать модуль nx в конфигурацию, выполните команду `Import-DSCResource`:</span><span class="sxs-lookup"><span data-stu-id="c3315-142">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="c3315-143">Определите конфигурацию и создайте документ конфигурации:</span><span class="sxs-lookup"><span data-stu-id="c3315-143">Define a configuration and generate the configuration document:</span></span>

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

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="c3315-144">Передача конфигурации на компьютер Linux</span><span class="sxs-lookup"><span data-stu-id="c3315-144">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="c3315-145">Документы конфигурации (MOF-файлы) можно принудительно отправить на компьютер Linux с помощью командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="c3315-145">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="c3315-146">Чтобы выполнить этот командлет, как и командлеты [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) или [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), удаленно на компьютере Linux, необходимо использовать CIMSession.</span><span class="sxs-lookup"><span data-stu-id="c3315-146">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="c3315-147">Для создания CIMSession на компьютере Linux служит командлет [New-CimSession](/powershell/module/CimCmdlets/New-CimSession).</span><span class="sxs-lookup"><span data-stu-id="c3315-147">The [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet is used to create a CIMSession to the Linux computer.</span></span>

<span data-ttu-id="c3315-148">Создание CIMSession в DSC для Linux демонстрируется в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c3315-148">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

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
> <span data-ttu-id="c3315-149">В режиме принудительной передачи необходимо указывать учетные данные привилегированного пользователя на компьютере Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-149">For "Push" mode, the user credential must be the root user on the Linux computer.</span></span>
> <span data-ttu-id="c3315-150">DSC для Linux поддерживает только SSL/TLS-подключения, поэтому необходимо использовать командлет `New-CimSession` с параметром –UseSSL, имеющим значение $true.</span><span class="sxs-lookup"><span data-stu-id="c3315-150">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span>
> <span data-ttu-id="c3315-151">SSL-сертификат, используемый OMI (DSC), указан в файле `/etc/opt/omi/conf/omiserver.conf` со свойствами pemfile и keyfile.</span><span class="sxs-lookup"><span data-stu-id="c3315-151">The SSL certificate used by OMI (for DSC) is specified in the file: `/etc/opt/omi/conf/omiserver.conf` with the properties: pemfile and keyfile.</span></span>
> <span data-ttu-id="c3315-152">Если компьютер Windows, на котором выполняется командлет [New-CimSession](/powershell/module/CimCmdlets/New-CimSession), не признает этот сертификат как надежный, проверку сертификата можно пропустить, используя параметры CIMSession: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span><span class="sxs-lookup"><span data-stu-id="c3315-152">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span></span>

<span data-ttu-id="c3315-153">Для принудительной отправки конфигурации DSC на узел Linux используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c3315-153">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession $Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="c3315-154">Распространение конфигурации через опрашивающий сервер</span><span class="sxs-lookup"><span data-stu-id="c3315-154">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="c3315-155">Конфигурации можно распространять на компьютер Linux через опрашивающий сервер, как и в случае компьютеров с Windows.</span><span class="sxs-lookup"><span data-stu-id="c3315-155">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="c3315-156">Рекомендации по работе с опрашивающим сервером см. в статье [Опрашивающие серверы настройки требуемого состояния Windows PowerShell](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="c3315-156">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](../pull-server/pullServer.md).</span></span> <span data-ttu-id="c3315-157">Дополнительные сведения и ограничения, связанные с использованием компьютеров Linux с опрашивающим сервером, см. в заметках о выпуске настройки требуемого состояния для Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-157">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="c3315-158">Локальная работа с конфигурациями</span><span class="sxs-lookup"><span data-stu-id="c3315-158">Working with configurations locally</span></span>

<span data-ttu-id="c3315-159">DSC для Linux включает сценарии работы с конфигурацией на локальном компьютере Linux.</span><span class="sxs-lookup"><span data-stu-id="c3315-159">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="c3315-160">Эти сценарии расположены в `/opt/microsoft/dsc/Scripts` и включают следующее:</span><span class="sxs-lookup"><span data-stu-id="c3315-160">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="c3315-161">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="c3315-161">GetDscConfiguration.py</span></span>

<span data-ttu-id="c3315-162">Возвращает текущую конфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c3315-162">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="c3315-163">Аналог командлета `Get-DscConfiguration` в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3315-163">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

`# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="c3315-164">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="c3315-164">GetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="c3315-165">Возвращает текущую метаконфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c3315-165">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="c3315-166">Аналог командлета [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="c3315-166">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

`# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="c3315-167">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="c3315-167">InstallModule.py</span></span>

<span data-ttu-id="c3315-168">Устанавливает пользовательский модуль ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="c3315-168">Installs a custom DSC resource module.</span></span> <span data-ttu-id="c3315-169">Необходим путь к ZIP-файлу, содержащему библиотеку общих объектов модуля и MOF-файлы схемы.</span><span class="sxs-lookup"><span data-stu-id="c3315-169">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

`# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="c3315-170">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="c3315-170">RemoveModule.py</span></span>

<span data-ttu-id="c3315-171">Удаляет пользовательский модуль ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="c3315-171">Removes a custom DSC resource module.</span></span> <span data-ttu-id="c3315-172">Требуется имя модуля, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="c3315-172">Requires the name of the module to remove.</span></span>

`# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="c3315-173">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="c3315-173">StartDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="c3315-174">Применяет MOF-файл конфигурации к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c3315-174">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="c3315-175">Аналог командлета [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="c3315-175">Similar to the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="c3315-176">Требуется путь к соответствующему MOF-файлу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3315-176">Requires the path to the configuration MOF to apply.</span></span>

`# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="c3315-177">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="c3315-177">SetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="c3315-178">Применяет MOF-файл метаконфигурации к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c3315-178">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="c3315-179">Аналог командлета [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="c3315-179">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="c3315-180">Требуется путь к соответствующему MOF-файлу метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3315-180">Requires the path to the Meta Configuration MOF to apply.</span></span>

`# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="c3315-181">Настройка требуемого состояния Windows PowerShell для файлов журнала Linux</span><span class="sxs-lookup"><span data-stu-id="c3315-181">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="c3315-182">Для сообщений DSC для Linux формируются следующие файлы журналов:</span><span class="sxs-lookup"><span data-stu-id="c3315-182">The following log files are generated for DSC for Linux messages.</span></span>

|<span data-ttu-id="c3315-183">Файл журнала</span><span class="sxs-lookup"><span data-stu-id="c3315-183">Log file</span></span>|<span data-ttu-id="c3315-184">Каталог</span><span class="sxs-lookup"><span data-stu-id="c3315-184">Directory</span></span>|<span data-ttu-id="c3315-185">Описание</span><span class="sxs-lookup"><span data-stu-id="c3315-185">Description</span></span>|
|---|---|---|
|<span data-ttu-id="c3315-186">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="c3315-186">**omiserver.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="c3315-187">Сообщения, относящиеся к работе сервера OMI CIM.</span><span class="sxs-lookup"><span data-stu-id="c3315-187">Messages relating to the operation of the OMI CIM server.</span></span>|
|<span data-ttu-id="c3315-188">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="c3315-188">**dsc.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="c3315-189">Сообщения, относящиеся к работе локального диспетчера конфигураций (LCM) и операциям с ресурсами DSC.</span><span class="sxs-lookup"><span data-stu-id="c3315-189">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span>|
