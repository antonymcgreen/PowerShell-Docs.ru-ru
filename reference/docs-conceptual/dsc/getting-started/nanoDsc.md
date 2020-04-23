---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Использование DSC на сервере Nano Server
ms.openlocfilehash: fb826455c21833ae4c8dc2ecd731ffce6bf7eaba
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953861"
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="6e371-103">Использование DSC на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="6e371-103">Using DSC on Nano Server</span></span>

> <span data-ttu-id="6e371-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6e371-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="6e371-105">**DSC для Nano Server** — это дополнительный пакет в папке `NanoServer\Packages` носителей Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="6e371-105">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="6e371-106">Пакет можно установить при создании виртуального жесткого диска для сервера Nano Server, указав значение **Microsoft-NanoServer-DSC-Package** для параметра **Packages** функции **New-NanoServerImage**.</span><span class="sxs-lookup"><span data-stu-id="6e371-106">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="6e371-107">Например, при создании виртуального жесткого диска для виртуальной машины команда будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6e371-107">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="6e371-108">Сведения об установке и использовании сервера Nano Server, а также об управлении этим сервером с помощью удаленного взаимодействия PowerShell см. в статье [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server) (Приступая к работе с сервером Nano Server).</span><span class="sxs-lookup"><span data-stu-id="6e371-108">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server).</span></span>

## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="6e371-109">Функции DSC, доступные на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="6e371-109">DSC features available on Nano Server</span></span>

<span data-ttu-id="6e371-110">Так как сервер Nano Server поддерживает только ограниченный набор API по сравнению с полной версией Windows Server, набор функций DSC в системе Nano Server на данный момент несравним с DSC в полнофункциональных SKU.</span><span class="sxs-lookup"><span data-stu-id="6e371-110">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="6e371-111">DSC для Nano Server в настоящее время активно разрабатывается и не является законченным компонентом.</span><span class="sxs-lookup"><span data-stu-id="6e371-111">DSC on Nano Server is in active development and is not yet feature complete.</span></span>

<span data-ttu-id="6e371-112">Следующие функции DSC в настоящее время доступны для Nano Server:</span><span class="sxs-lookup"><span data-stu-id="6e371-112">The following DSC features are currently available on Nano Server:</span></span>

<span data-ttu-id="6e371-113">Режимы опроса и принудительной отправки</span><span class="sxs-lookup"><span data-stu-id="6e371-113">Both push and pull modes</span></span>

- <span data-ttu-id="6e371-114">Все командлеты DSC, которые существуют в полной версии Windows Server, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="6e371-114">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span>
- [<span data-ttu-id="6e371-115">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="6e371-115">Get-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager)
- [<span data-ttu-id="6e371-116">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="6e371-116">Set-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager)
- [<span data-ttu-id="6e371-117">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="6e371-117">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
- [<span data-ttu-id="6e371-118">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="6e371-118">Disable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug)
- [<span data-ttu-id="6e371-119">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-119">Start-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)
- [<span data-ttu-id="6e371-120">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-120">Stop-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)
- [<span data-ttu-id="6e371-121">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-121">Get-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)
- [<span data-ttu-id="6e371-122">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-122">Test-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)
- [<span data-ttu-id="6e371-123">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-123">Publish-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)
- [<span data-ttu-id="6e371-124">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-124">Update-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration)
- [<span data-ttu-id="6e371-125">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e371-125">Restore-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Restore-DscConfiguration)
- [<span data-ttu-id="6e371-126">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="6e371-126">Remove-DscConfigurationDocument</span></span>](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)
- [<span data-ttu-id="6e371-127">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="6e371-127">Get-DscConfigurationStatus</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)
- [<span data-ttu-id="6e371-128">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="6e371-128">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
- [<span data-ttu-id="6e371-129">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="6e371-129">Find-DscResource</span></span>](/powershell/module/powershellget/find-dscresource?view=powershell-6)
- [<span data-ttu-id="6e371-130">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="6e371-130">Get-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)
- [<span data-ttu-id="6e371-131">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="6e371-131">New-DscChecksum</span></span>](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)

- <span data-ttu-id="6e371-132">Компиляция конфигураций (см. раздел [Конфигурации DSC](../configurations/configurations.md)).</span><span class="sxs-lookup"><span data-stu-id="6e371-132">Compiling configurations (see [DSC configurations](../configurations/configurations.md))</span></span>

  <span data-ttu-id="6e371-133">**Проблема**. Не работает шифрование паролей (см. раздел [Защита MOF-файла](../pull-server/secureMOF.md)) во время компиляции конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6e371-133">**Issue:** Password encryption (see [Securing the MOF File](../pull-server/secureMOF.md)) during configuration compilation doesn't work.</span></span>

- <span data-ttu-id="6e371-134">Компиляция метаконфигураций (см. раздел [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md)).</span><span class="sxs-lookup"><span data-stu-id="6e371-134">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md))</span></span>

- <span data-ttu-id="6e371-135">Выполнение ресурса в контексте пользователя (см. раздел [Запуск DSC с учетными данными пользователя (запуск от имени)](../configurations/runAsUser.md)).</span><span class="sxs-lookup"><span data-stu-id="6e371-135">Running a resource under user context (see [Running DSC with user credentials (RunAs)](../configurations/runAsUser.md))</span></span>

- <span data-ttu-id="6e371-136">Ресурсы на основе класса (см. раздел [Написание пользовательских ресурсов DSC с использованием классов PowerShell](/previous-versions//dn948461(v=technet.10))).</span><span class="sxs-lookup"><span data-stu-id="6e371-136">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](/previous-versions//dn948461(v=technet.10)))</span></span>

- <span data-ttu-id="6e371-137">Отладка ресурсов DSC (см. раздел [Отладка ресурсов DSC](../troubleshooting/debugResource.md)).</span><span class="sxs-lookup"><span data-stu-id="6e371-137">Debugging of DSC resources (see [Debugging DSC resources](../troubleshooting/debugResource.md))</span></span>

  <span data-ttu-id="6e371-138">**Проблема**. Отладка не работает, если ресурс использует PsDscRunAsCredential (см. раздел [Запуск DSC с учетными данными пользователя](../configurations/runAsUser.md)).</span><span class="sxs-lookup"><span data-stu-id="6e371-138">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](../configurations/runAsUser.md))</span></span>

- [<span data-ttu-id="6e371-139">Указание межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="6e371-139">Specifying cross-node dependencies</span></span>](../configurations/crossNodeDependencies.md)

- [<span data-ttu-id="6e371-140">Управление версиями ресурсов</span><span class="sxs-lookup"><span data-stu-id="6e371-140">Resource versioning</span></span>](../configurations/sxsResource.md)

- <span data-ttu-id="6e371-141">Опрашивающий клиент (конфигурации и ресурсы) (см. раздел [Настройка опрашивающего клиента с помощью имен конфигураций](../pull-server/pullClientConfigNames.md)).</span><span class="sxs-lookup"><span data-stu-id="6e371-141">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](../pull-server/pullClientConfigNames.md))</span></span>

- [<span data-ttu-id="6e371-142">Частичные конфигурации (по запросу и принудительная отправка)</span><span class="sxs-lookup"><span data-stu-id="6e371-142">Partial configurations (pull & push)</span></span>](../pull-server/partialConfigs.md)

- [<span data-ttu-id="6e371-143">Передача отчетов на опрашивающий сервер</span><span class="sxs-lookup"><span data-stu-id="6e371-143">Reporting to pull server</span></span>](../pull-server/reportServer.md)

- <span data-ttu-id="6e371-144">Шифрование MOF-файлов</span><span class="sxs-lookup"><span data-stu-id="6e371-144">MOF encryption</span></span>

- <span data-ttu-id="6e371-145">ведение журнала событий.</span><span class="sxs-lookup"><span data-stu-id="6e371-145">Event logging</span></span>

- <span data-ttu-id="6e371-146">Отчеты DSC службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="6e371-146">Azure Automation DSC reporting</span></span>

- <span data-ttu-id="6e371-147">Полнофункциональные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6e371-147">Resources that are fully functional</span></span>

- <span data-ttu-id="6e371-148">**Архив**</span><span class="sxs-lookup"><span data-stu-id="6e371-148">**Archive**</span></span>
- <span data-ttu-id="6e371-149">**Среда**</span><span class="sxs-lookup"><span data-stu-id="6e371-149">**Environment**</span></span>
- <span data-ttu-id="6e371-150">**Файл**</span><span class="sxs-lookup"><span data-stu-id="6e371-150">**File**</span></span>
- <span data-ttu-id="6e371-151">**Журнал**</span><span class="sxs-lookup"><span data-stu-id="6e371-151">**Log**</span></span>
- <span data-ttu-id="6e371-152">**ProcessSet**</span><span class="sxs-lookup"><span data-stu-id="6e371-152">**ProcessSet**</span></span>
- <span data-ttu-id="6e371-153">**Реестр**</span><span class="sxs-lookup"><span data-stu-id="6e371-153">**Registry**</span></span>
- <span data-ttu-id="6e371-154">**Скрипт**</span><span class="sxs-lookup"><span data-stu-id="6e371-154">**Script**</span></span>
- <span data-ttu-id="6e371-155">**WindowsPackageCab**</span><span class="sxs-lookup"><span data-stu-id="6e371-155">**WindowsPackageCab**</span></span>
- <span data-ttu-id="6e371-156">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="6e371-156">**WindowsProcess**</span></span>
- <span data-ttu-id="6e371-157">**WaitForAll** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="6e371-157">**WaitForAll** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
- <span data-ttu-id="6e371-158">**WaitForAny** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="6e371-158">**WaitForAny** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
- <span data-ttu-id="6e371-159">**WaitForSome** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="6e371-159">**WaitForSome** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>

- <span data-ttu-id="6e371-160">Ресурсы, функциональность которых не полная.</span><span class="sxs-lookup"><span data-stu-id="6e371-160">Resources that are partially functional</span></span>
- <span data-ttu-id="6e371-161">**Группирование**</span><span class="sxs-lookup"><span data-stu-id="6e371-161">**Group**</span></span>
- <span data-ttu-id="6e371-162">**GroupSet**</span><span class="sxs-lookup"><span data-stu-id="6e371-162">**GroupSet**</span></span>

  <span data-ttu-id="6e371-163">**Проблема**. Приведенные выше ресурсы не работают, если определенный экземпляр вызывается дважды (дважды запускается одна и та же конфигурация).</span><span class="sxs-lookup"><span data-stu-id="6e371-163">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>

- <span data-ttu-id="6e371-164">**Служба**</span><span class="sxs-lookup"><span data-stu-id="6e371-164">**Service**</span></span>
- <span data-ttu-id="6e371-165">**ServiceSet**</span><span class="sxs-lookup"><span data-stu-id="6e371-165">**ServiceSet**</span></span>

  <span data-ttu-id="6e371-166">**Проблема**. Работает только для запуска или остановки службы (атрибут status).</span><span class="sxs-lookup"><span data-stu-id="6e371-166">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="6e371-167">Не работает при попытке изменить другие атрибуты службы, например startuptype, credentials, description и т. д.</span><span class="sxs-lookup"><span data-stu-id="6e371-167">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="6e371-168">Возникает ошибка такого вида.</span><span class="sxs-lookup"><span data-stu-id="6e371-168">The error thrown is similar to:</span></span>

  <span data-ttu-id="6e371-169">*Не удается найти тип [management.managementobject]: убедитесь в том, что сборка, содержащая этот тип, загружена.*</span><span class="sxs-lookup"><span data-stu-id="6e371-169">*Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.*</span></span>

- <span data-ttu-id="6e371-170">Нефункционирующие ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6e371-170">Resources that are not functional</span></span>
- <span data-ttu-id="6e371-171">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="6e371-171">**User**</span></span>

## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="6e371-172">Функции DSC, недоступные на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="6e371-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="6e371-173">Следующие функции DSC в настоящее время недоступны для Nano Server:</span><span class="sxs-lookup"><span data-stu-id="6e371-173">The following DSC features are not currently available on Nano Server:</span></span>

- <span data-ttu-id="6e371-174">Расшифровка документа MOF с помощью зашифрованных паролей.</span><span class="sxs-lookup"><span data-stu-id="6e371-174">Decrypting MOF document with encrypted password(s)</span></span>
- <span data-ttu-id="6e371-175">Опрашивающий сервер — в настоящее время опрашивающий сервер нельзя настроить на сервере Nano Server.</span><span class="sxs-lookup"><span data-stu-id="6e371-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
- <span data-ttu-id="6e371-176">Все компоненты, не указанные в списке функций, работают.</span><span class="sxs-lookup"><span data-stu-id="6e371-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="6e371-177">Использование настраиваемых ресурсов DSC на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="6e371-177">Using custom DSC resources on Nano Server</span></span>

<span data-ttu-id="6e371-178">Поскольку набор API Windows и библиотек CLR, доступный на сервере Nano Server, ограничен, ресурсы DSC, работающие в полной версии среды выполнения Windows, не всегда работают в Nano Server.</span><span class="sxs-lookup"><span data-stu-id="6e371-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span>
<span data-ttu-id="6e371-179">Перед развертыванием каких-либо настраиваемых ресурсов DSC в рабочей среде рекомендуется выполнять их полное и всестороннее тестирование.</span><span class="sxs-lookup"><span data-stu-id="6e371-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e371-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e371-180">See Also</span></span>

- [<span data-ttu-id="6e371-181">Начало работы с сервером Nano Server</span><span class="sxs-lookup"><span data-stu-id="6e371-181">Getting Started with Nano Server</span></span>](/windows-server/get-started/getting-started-with-nano-server)
