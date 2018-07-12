---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Начало работы с настройкой требуемого состояния (DSC) для Linux
ms.openlocfilehash: d5a4a17fbcffbbbd6df3dd902dbd104769b7d17e
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893602"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="a86ca-103">Начало работы с настройкой требуемого состояния (DSC) для Linux</span><span class="sxs-lookup"><span data-stu-id="a86ca-103">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="a86ca-104">В этом разделе объясняется, как приступить к работе с настройкой требуемого состояния PowerShell (DSC) для Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span> <span data-ttu-id="a86ca-105">Общие сведения о службе настройки требуемого состояния см. в разделе [Начало работы со службой настройки требуемого состояния Windows PowerShell](overview.md).</span><span class="sxs-lookup"><span data-stu-id="a86ca-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="a86ca-106">Поддерживаемые версии операционной системы Linux</span><span class="sxs-lookup"><span data-stu-id="a86ca-106">Supported Linux operation system versions</span></span>

<span data-ttu-id="a86ca-107">DSC для Linux поддерживает следующие версии операционной системы Linux:</span><span class="sxs-lookup"><span data-stu-id="a86ca-107">The following Linux operating system versions are supported for DSC for Linux.</span></span>

- <span data-ttu-id="a86ca-108">CentOS 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="a86ca-108">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="a86ca-109">Debian GNU/Linux 6, 7 и 8 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="a86ca-109">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="a86ca-110">Oracle Linux 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="a86ca-110">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="a86ca-111">Red Hat Enterprise Linux Server 5, 6 и 7 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="a86ca-111">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="a86ca-112">SUSE Linux Enterprise Server 10, 11 и 12 (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="a86ca-112">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="a86ca-113">Ubuntu Server 12.04 LTS, 14.04 LTS и 16.04 LTS (x86 и x64)</span><span class="sxs-lookup"><span data-stu-id="a86ca-113">Ubuntu Server 12.04 LTS, 14.04 LTS and 16.04 LTS (x86/x64)</span></span>

<span data-ttu-id="a86ca-114">Ниже указано, какие зависимости пакетов необходимы DSC для Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-114">The following table describes the required package dependencies for DSC for Linux.</span></span>

|  <span data-ttu-id="a86ca-115">Требуемый пакет</span><span class="sxs-lookup"><span data-stu-id="a86ca-115">Required package</span></span> |  <span data-ttu-id="a86ca-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a86ca-116">Description</span></span> |  <span data-ttu-id="a86ca-117">Минимальная версия</span><span class="sxs-lookup"><span data-stu-id="a86ca-117">Minimum version</span></span> |
|---|---|---|
| <span data-ttu-id="a86ca-118">glibc</span><span class="sxs-lookup"><span data-stu-id="a86ca-118">glibc</span></span>| <span data-ttu-id="a86ca-119">Библиотека GNU</span><span class="sxs-lookup"><span data-stu-id="a86ca-119">GNU Library</span></span>| <span data-ttu-id="a86ca-120">2…4 — 31.30</span><span class="sxs-lookup"><span data-stu-id="a86ca-120">2…4 – 31.30</span></span>|
| <span data-ttu-id="a86ca-121">python</span><span class="sxs-lookup"><span data-stu-id="a86ca-121">python</span></span>| <span data-ttu-id="a86ca-122">Python</span><span class="sxs-lookup"><span data-stu-id="a86ca-122">Python</span></span>| <span data-ttu-id="a86ca-123">2.4 — 3.4</span><span class="sxs-lookup"><span data-stu-id="a86ca-123">2.4 – 3.4</span></span>|
| <span data-ttu-id="a86ca-124">omiserver</span><span class="sxs-lookup"><span data-stu-id="a86ca-124">omiserver</span></span>| <span data-ttu-id="a86ca-125">Открытая инфраструктура управления</span><span class="sxs-lookup"><span data-stu-id="a86ca-125">Open Management Infrastructure</span></span>| <span data-ttu-id="a86ca-126">1.0.8.1</span><span class="sxs-lookup"><span data-stu-id="a86ca-126">1.0.8.1</span></span>|
| <span data-ttu-id="a86ca-127">openssl</span><span class="sxs-lookup"><span data-stu-id="a86ca-127">openssl</span></span>| <span data-ttu-id="a86ca-128">Библиотеки OpenSSL</span><span class="sxs-lookup"><span data-stu-id="a86ca-128">OpenSSL Libraries</span></span>| <span data-ttu-id="a86ca-129">0.9.8 или 1.0</span><span class="sxs-lookup"><span data-stu-id="a86ca-129">0.9.8 or 1.0</span></span>|
| <span data-ttu-id="a86ca-130">ctypes</span><span class="sxs-lookup"><span data-stu-id="a86ca-130">ctypes</span></span>| <span data-ttu-id="a86ca-131">Библиотека Python CTypes</span><span class="sxs-lookup"><span data-stu-id="a86ca-131">Python CTypes library</span></span>| <span data-ttu-id="a86ca-132">Должна соответствовать версии Python</span><span class="sxs-lookup"><span data-stu-id="a86ca-132">Must match Python version</span></span>|
| <span data-ttu-id="a86ca-133">libcurl</span><span class="sxs-lookup"><span data-stu-id="a86ca-133">libcurl</span></span>| <span data-ttu-id="a86ca-134">Библиотека HTTP-клиентов cURL</span><span class="sxs-lookup"><span data-stu-id="a86ca-134">cURL http client library</span></span>| <span data-ttu-id="a86ca-135">7.15.1</span><span class="sxs-lookup"><span data-stu-id="a86ca-135">7.15.1</span></span>|

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="a86ca-136">Установка DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="a86ca-136">Installing DSC for Linux</span></span>

<span data-ttu-id="a86ca-137">Перед установкой DSC для Linux необходимо установить [открытую инфраструктуру управления (OMI)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="a86ca-137">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="a86ca-138">Установка OMI</span><span class="sxs-lookup"><span data-stu-id="a86ca-138">Installing OMI</span></span>

<span data-ttu-id="a86ca-139">Настройка требуемого состояния для Linux требует наличия CIM-сервера открытой инфраструктуры управления (OMI) версии 1.0.8.1 и выше.</span><span class="sxs-lookup"><span data-stu-id="a86ca-139">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="a86ca-140">OMI можно загрузить из Open Group: [Открытая инфраструктура управления (OMI)](https://github.com/Microsoft/omi).</span><span class="sxs-lookup"><span data-stu-id="a86ca-140">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="a86ca-141">Чтобы установить OMI, установите пакет, соответствующий вашей системе Linux (RPM или DEB), а также версии OpenSSL (ssl_098 или ssl_100) и архитектуре (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="a86ca-141">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="a86ca-142">Пакеты RPM подходят для CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-142">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="a86ca-143">Пакеты DEB подходят для Debian GNU/Linux и Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="a86ca-143">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="a86ca-144">Пакеты ssl_098 подходят для компьютеров с установленным OpenSSL 0.9.8, а пакеты ssl_100 — для компьютеров с установленным OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="a86ca-144">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="a86ca-145">Чтобы определить установленную версию OpenSSL, выполните команду `openssl version`.</span><span class="sxs-lookup"><span data-stu-id="a86ca-145">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="a86ca-146">Выполните указанную ниже команду для установки OMI в системе CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="a86ca-146">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="a86ca-147">Установка DSC</span><span class="sxs-lookup"><span data-stu-id="a86ca-147">Installing DSC</span></span>

<span data-ttu-id="a86ca-148">DSC для Linux можно скачать [здесь](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span><span class="sxs-lookup"><span data-stu-id="a86ca-148">DSC for Linux is available for download [here](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span></span>

<span data-ttu-id="a86ca-149">Чтобы установить DSC, установите пакет, соответствующий вашей системе Linux (RPM или DEB), а также версии OpenSSL (ssl_098 или ssl_100) и архитектуре (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="a86ca-149">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="a86ca-150">Пакеты RPM подходят для CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-150">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="a86ca-151">Пакеты DEB подходят для Debian GNU/Linux и Ubuntu Server.</span><span class="sxs-lookup"><span data-stu-id="a86ca-151">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="a86ca-152">Пакеты ssl_098 подходят для компьютеров с установленным OpenSSL 0.9.8, а пакеты ssl_100 — для компьютеров с установленным OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="a86ca-152">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="a86ca-153">Чтобы определить установленную версию OpenSSL, выполните команду openssl.</span><span class="sxs-lookup"><span data-stu-id="a86ca-153">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="a86ca-154">Выполните указанную ниже команду для установки DSC в системе CentOS 7 x64.</span><span class="sxs-lookup"><span data-stu-id="a86ca-154">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="a86ca-155">Использование DSC для Linux</span><span class="sxs-lookup"><span data-stu-id="a86ca-155">Using DSC for Linux</span></span>

<span data-ttu-id="a86ca-156">В следующих разделах описывается создание и запуск конфигураций DSC на компьютерах Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-156">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="a86ca-157">Создание MOF-документа конфигурации</span><span class="sxs-lookup"><span data-stu-id="a86ca-157">Creating a configuration MOF document</span></span>

<span data-ttu-id="a86ca-158">На компьютерах Linux (как и на компьютерах Windows) для создания конфигурации используется ключевое слово конфигурации Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a86ca-158">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="a86ca-159">Следующие шаги описывают создание документа конфигурации для компьютера Linux с использованием Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a86ca-159">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="a86ca-160">Импортируйте модуль nx.</span><span class="sxs-lookup"><span data-stu-id="a86ca-160">Import the nx module.</span></span> <span data-ttu-id="a86ca-161">Модуль nx для Windows PowerShell содержит схему для встроенных ресурсов DSC в Linux, поэтому он должен быть установлен на локальном компьютере и импортирован в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a86ca-161">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="a86ca-162">Чтобы установить модуль nx, скопируйте каталог модуля nx в `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` или в `$PSHOME\Modules`.</span><span class="sxs-lookup"><span data-stu-id="a86ca-162">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="a86ca-163">Модуль nx включается в пакет установки DSC для Linux (MSI).</span><span class="sxs-lookup"><span data-stu-id="a86ca-163">The nx module is included in the DSC for Linux installation package (MSI).</span></span> <span data-ttu-id="a86ca-164">Чтобы импортировать модуль nx в конфигурацию, выполните команду `Import-DSCResource`:</span><span class="sxs-lookup"><span data-stu-id="a86ca-164">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="a86ca-165">Определите конфигурацию и создайте документ конфигурации:</span><span class="sxs-lookup"><span data-stu-id="a86ca-165">Define a configuration and generate the configuration document:</span></span>

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

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="a86ca-166">Передача конфигурации на компьютер Linux</span><span class="sxs-lookup"><span data-stu-id="a86ca-166">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="a86ca-167">Документы конфигурации (MOF-файлы) можно принудительно отправить на компьютер Linux с помощью командлета [Start-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Start-DscConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a86ca-167">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Start-DscConfiguration) cmdlet.</span></span> <span data-ttu-id="a86ca-168">Чтобы выполнить этот командлет, как и командлеты [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) или [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration), удаленно на компьютере Linux, необходимо использовать CIMSession.</span><span class="sxs-lookup"><span data-stu-id="a86ca-168">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="a86ca-169">Для создания CIMSession на компьютере Linux служит командлет [New-CimSession](http://go.microsoft.com/fwlink/?LinkId=227967).</span><span class="sxs-lookup"><span data-stu-id="a86ca-169">The [New-CimSession](http://go.microsoft.com/fwlink/?LinkId=227967) cmdlet is used to create a CIMSession to the Linux computer.</span></span>

<span data-ttu-id="a86ca-170">Создание CIMSession в DSC для Linux демонстрируется в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a86ca-170">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

```powershell
$Node = "ostc-dsc-01"
$Credential = Get-Credential -UserName:"root" -Message:"Enter Password:"

#Ignore SSL certificate validation
#$opt = New-CimSessionOption -UseSsl:$true -SkipCACheck:$true -SkipCNCheck:$true -SkipRevocationCheck:$true

#Options for a trusted SSL certificate
$opt = New-CimSessionOption -UseSsl:$true
$Sess=New-CimSession -Credential:$credential -ComputerName:$Node -Port:5986 -Authentication:basic -SessionOption:$opt -OperationTimeoutSec:90
```

> [!NOTE]
> <span data-ttu-id="a86ca-171">В режиме принудительной передачи необходимо указывать учетные данные привилегированного пользователя на компьютере Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-171">For “Push” mode, the user credential must be the root user on the Linux computer.</span></span>
> <span data-ttu-id="a86ca-172">DSC для Linux поддерживает только SSL/TLS-подключения, поэтому необходимо использовать командлет `New-CimSession` с параметром –UseSSL, имеющим значение $true.</span><span class="sxs-lookup"><span data-stu-id="a86ca-172">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span>
> <span data-ttu-id="a86ca-173">SSL-сертификат, используемый OMI (DSC), указан в файле `/opt/omi/etc/omiserver.conf` со свойствами pemfile и keyfile.</span><span class="sxs-lookup"><span data-stu-id="a86ca-173">The SSL certificate used by OMI (for DSC) is specified in the file: `/opt/omi/etc/omiserver.conf` with the properties: pemfile and keyfile.</span></span>
> <span data-ttu-id="a86ca-174">Если компьютер Windows, на котором выполняется командлет [New-CimSession](http://go.microsoft.com/fwlink/?LinkId=227967), не признает этот сертификат как надежный, проверку сертификата можно пропустить, используя параметры CIMSession: `-SkipCACheck:$true -SkipCNCheck:$true -SkipRevocationCheck:$true`</span><span class="sxs-lookup"><span data-stu-id="a86ca-174">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](http://go.microsoft.com/fwlink/?LinkId=227967) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck:$true -SkipCNCheck:$true -SkipRevocationCheck:$true`</span></span>

<span data-ttu-id="a86ca-175">Для принудительной отправки конфигурации DSC на узел Linux используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a86ca-175">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession:$Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="a86ca-176">Распространение конфигурации через опрашивающий сервер</span><span class="sxs-lookup"><span data-stu-id="a86ca-176">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="a86ca-177">Конфигурации можно распространять на компьютер Linux через опрашивающий сервер, как и в случае компьютеров с Windows.</span><span class="sxs-lookup"><span data-stu-id="a86ca-177">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="a86ca-178">Рекомендации по работе с опрашивающим сервером см. в статье [Опрашивающие серверы конфигурации требуемого состояния Windows PowerShell](pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="a86ca-178">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](pullServer.md).</span></span> <span data-ttu-id="a86ca-179">Дополнительные сведения и ограничения, связанные с использованием компьютеров Linux с опрашивающим сервером, см. в заметках о выпуске настройки требуемого состояния для Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-179">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="a86ca-180">Локальная работа с конфигурациями</span><span class="sxs-lookup"><span data-stu-id="a86ca-180">Working with configurations locally</span></span>

<span data-ttu-id="a86ca-181">DSC для Linux включает сценарии работы с конфигурацией на локальном компьютере Linux.</span><span class="sxs-lookup"><span data-stu-id="a86ca-181">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="a86ca-182">Эти сценарии расположены в `/opt/microsoft/dsc/Scripts` и включают следующее:</span><span class="sxs-lookup"><span data-stu-id="a86ca-182">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="a86ca-183">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="a86ca-183">GetDscConfiguration.py</span></span>

<span data-ttu-id="a86ca-184">Возвращает текущую конфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a86ca-184">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="a86ca-185">Аналог командлета `Get-DscConfiguration` в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a86ca-185">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

`# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="a86ca-186">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="a86ca-186">GetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="a86ca-187">Возвращает текущую метаконфигурацию, примененную к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a86ca-187">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="a86ca-188">Аналог командлета [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="a86ca-188">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

`# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="a86ca-189">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="a86ca-189">InstallModule.py</span></span>

<span data-ttu-id="a86ca-190">Устанавливает пользовательский модуль ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="a86ca-190">Installs a custom DSC resource module.</span></span> <span data-ttu-id="a86ca-191">Необходим путь к ZIP-файлу, содержащему библиотеку общих объектов модуля и MOF-файлы схемы.</span><span class="sxs-lookup"><span data-stu-id="a86ca-191">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

`# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="a86ca-192">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="a86ca-192">RemoveModule.py</span></span>

<span data-ttu-id="a86ca-193">Удаляет пользовательский модуль ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="a86ca-193">Removes a custom DSC resource module.</span></span> <span data-ttu-id="a86ca-194">Требуется имя модуля, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="a86ca-194">Requires the name of the module to remove.</span></span>

`# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="a86ca-195">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="a86ca-195">StartDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="a86ca-196">Применяет MOF-файл конфигурации к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a86ca-196">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="a86ca-197">Аналог командлета [Start-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Start-DscConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a86ca-197">Similar to the [Start-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Start-DscConfiguration) cmdlet.</span></span> <span data-ttu-id="a86ca-198">Требуется путь к соответствующему MOF-файлу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a86ca-198">Requires the path to the configuration MOF to apply.</span></span>

`# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="a86ca-199">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="a86ca-199">SetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="a86ca-200">Применяет MOF-файл метаконфигурации к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a86ca-200">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="a86ca-201">Аналог командлета [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="a86ca-201">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="a86ca-202">Требуется путь к соответствующему MOF-файлу метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="a86ca-202">Requires the path to the Meta Configuration MOF to apply.</span></span>

`# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="a86ca-203">Настройка требуемого состояния Windows PowerShell для файлов журнала Linux</span><span class="sxs-lookup"><span data-stu-id="a86ca-203">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="a86ca-204">Для сообщений DSC для Linux формируются следующие файлы журналов:</span><span class="sxs-lookup"><span data-stu-id="a86ca-204">The following log files are generated for DSC for Linux messages.</span></span>

|<span data-ttu-id="a86ca-205">Файл журнала</span><span class="sxs-lookup"><span data-stu-id="a86ca-205">Log file</span></span>|<span data-ttu-id="a86ca-206">Directory</span><span class="sxs-lookup"><span data-stu-id="a86ca-206">Directory</span></span>|<span data-ttu-id="a86ca-207">Описание</span><span class="sxs-lookup"><span data-stu-id="a86ca-207">Description</span></span>|
|---|---|---|
|<span data-ttu-id="a86ca-208">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="a86ca-208">**omiserver.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="a86ca-209">Сообщения, относящиеся к работе сервера OMI CIM.</span><span class="sxs-lookup"><span data-stu-id="a86ca-209">Messages relating to the operation of the OMI CIM server.</span></span>|
|<span data-ttu-id="a86ca-210">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="a86ca-210">**dsc.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="a86ca-211">Сообщения, относящиеся к работе локального диспетчера конфигураций (LCM) и операциям с ресурсами DSC.</span><span class="sxs-lookup"><span data-stu-id="a86ca-211">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span>|