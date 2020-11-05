---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Использование DSC на сервере Nano Server
description: DSC — это дополнительный пакет, который можно установить при создании VHD для Windows Nano Server.
ms.openlocfilehash: 18585323359abd85515d4db194dae4adbad7c3d8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92647075"
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="53e19-104">Использование DSC на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="53e19-104">Using DSC on Nano Server</span></span>

> <span data-ttu-id="53e19-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="53e19-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="53e19-106">**DSC для Nano Server**  — это дополнительный пакет в папке `NanoServer\Packages` носителей Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="53e19-106">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="53e19-107">Пакет можно установить при создании виртуального жесткого диска для сервера Nano Server, указав значение **Microsoft-NanoServer-DSC-Package** для параметра **Packages** функции **New-NanoServerImage**.</span><span class="sxs-lookup"><span data-stu-id="53e19-107">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="53e19-108">Например, при создании виртуального жесткого диска для виртуальной машины команда будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="53e19-108">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="53e19-109">Сведения об установке и использовании сервера Nano Server, а также об управлении этим сервером с помощью удаленного взаимодействия PowerShell см. в статье [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server) (Приступая к работе с сервером Nano Server).</span><span class="sxs-lookup"><span data-stu-id="53e19-109">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server).</span></span>

## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="53e19-110">Функции DSC, доступные на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="53e19-110">DSC features available on Nano Server</span></span>

<span data-ttu-id="53e19-111">Так как сервер Nano Server поддерживает только ограниченный набор API по сравнению с полной версией Windows Server, набор функций DSC в системе Nano Server на данный момент несравним с DSC в полнофункциональных SKU.</span><span class="sxs-lookup"><span data-stu-id="53e19-111">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="53e19-112">DSC для Nano Server в настоящее время активно разрабатывается и не является законченным компонентом.</span><span class="sxs-lookup"><span data-stu-id="53e19-112">DSC on Nano Server is in active development and is not yet feature complete.</span></span>

<span data-ttu-id="53e19-113">Следующие функции DSC в настоящее время доступны для Nano Server:</span><span class="sxs-lookup"><span data-stu-id="53e19-113">The following DSC features are currently available on Nano Server:</span></span>

<span data-ttu-id="53e19-114">Режимы опроса и принудительной отправки</span><span class="sxs-lookup"><span data-stu-id="53e19-114">Both push and pull modes</span></span>

- <span data-ttu-id="53e19-115">Все командлеты DSC, которые существуют в полной версии Windows Server, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="53e19-115">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span>
- [<span data-ttu-id="53e19-116">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="53e19-116">Get-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager)
- [<span data-ttu-id="53e19-117">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="53e19-117">Set-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager)
- [<span data-ttu-id="53e19-118">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="53e19-118">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
- [<span data-ttu-id="53e19-119">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="53e19-119">Disable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug)
- [<span data-ttu-id="53e19-120">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-120">Start-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)
- [<span data-ttu-id="53e19-121">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-121">Stop-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)
- [<span data-ttu-id="53e19-122">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-122">Get-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)
- [<span data-ttu-id="53e19-123">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-123">Test-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)
- [<span data-ttu-id="53e19-124">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-124">Publish-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)
- [<span data-ttu-id="53e19-125">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-125">Update-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration)
- [<span data-ttu-id="53e19-126">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="53e19-126">Restore-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Restore-DscConfiguration)
- [<span data-ttu-id="53e19-127">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="53e19-127">Remove-DscConfigurationDocument</span></span>](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)
- [<span data-ttu-id="53e19-128">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="53e19-128">Get-DscConfigurationStatus</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)
- [<span data-ttu-id="53e19-129">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="53e19-129">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
- [<span data-ttu-id="53e19-130">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="53e19-130">Find-DscResource</span></span>](/powershell/module/powershellget/find-dscresource)
- [<span data-ttu-id="53e19-131">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="53e19-131">Get-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)
- [<span data-ttu-id="53e19-132">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="53e19-132">New-DscChecksum</span></span>](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)

- <span data-ttu-id="53e19-133">Компиляция конфигураций (см. раздел [Конфигурации DSC](../configurations/configurations.md)).</span><span class="sxs-lookup"><span data-stu-id="53e19-133">Compiling configurations (see [DSC configurations](../configurations/configurations.md))</span></span>

  <span data-ttu-id="53e19-134">**Проблема**. Не работает шифрование паролей (см. раздел [Защита MOF-файла](../pull-server/secureMOF.md)) во время компиляции конфигурации.</span><span class="sxs-lookup"><span data-stu-id="53e19-134">**Issue:** Password encryption (see [Securing the MOF File](../pull-server/secureMOF.md)) during configuration compilation doesn't work.</span></span>

- <span data-ttu-id="53e19-135">Компиляция метаконфигураций (см. раздел [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md)).</span><span class="sxs-lookup"><span data-stu-id="53e19-135">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md))</span></span>

- <span data-ttu-id="53e19-136">Выполнение ресурса в контексте пользователя (см. раздел [Запуск DSC с учетными данными пользователя (запуск от имени)](../configurations/runAsUser.md)).</span><span class="sxs-lookup"><span data-stu-id="53e19-136">Running a resource under user context (see [Running DSC with user credentials (RunAs)](../configurations/runAsUser.md))</span></span>

- <span data-ttu-id="53e19-137">Ресурсы на основе класса (см. раздел [Написание пользовательских ресурсов DSC с использованием классов PowerShell](/previous-versions//dn948461(v=technet.10))).</span><span class="sxs-lookup"><span data-stu-id="53e19-137">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](/previous-versions//dn948461(v=technet.10)))</span></span>

- <span data-ttu-id="53e19-138">Отладка ресурсов DSC (см. раздел [Отладка ресурсов DSC](../troubleshooting/debugResource.md)).</span><span class="sxs-lookup"><span data-stu-id="53e19-138">Debugging of DSC resources (see [Debugging DSC resources](../troubleshooting/debugResource.md))</span></span>

  <span data-ttu-id="53e19-139">**Проблема**. Отладка не работает, если ресурс использует PsDscRunAsCredential (см. раздел [Запуск DSC с учетными данными пользователя](../configurations/runAsUser.md)).</span><span class="sxs-lookup"><span data-stu-id="53e19-139">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](../configurations/runAsUser.md))</span></span>

- [<span data-ttu-id="53e19-140">Указание межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="53e19-140">Specifying cross-node dependencies</span></span>](../configurations/crossNodeDependencies.md)

- [<span data-ttu-id="53e19-141">Управление версиями ресурсов</span><span class="sxs-lookup"><span data-stu-id="53e19-141">Resource versioning</span></span>](../configurations/sxsResource.md)

- <span data-ttu-id="53e19-142">Опрашивающий клиент (конфигурации и ресурсы) (см. раздел [Настройка опрашивающего клиента с помощью имен конфигураций](../pull-server/pullClientConfigNames.md)).</span><span class="sxs-lookup"><span data-stu-id="53e19-142">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](../pull-server/pullClientConfigNames.md))</span></span>

- [<span data-ttu-id="53e19-143">Частичные конфигурации (по запросу и принудительная отправка)</span><span class="sxs-lookup"><span data-stu-id="53e19-143">Partial configurations (pull & push)</span></span>](../pull-server/partialConfigs.md)

- [<span data-ttu-id="53e19-144">Передача отчетов на опрашивающий сервер</span><span class="sxs-lookup"><span data-stu-id="53e19-144">Reporting to pull server</span></span>](../pull-server/reportServer.md)

- <span data-ttu-id="53e19-145">Шифрование MOF-файлов</span><span class="sxs-lookup"><span data-stu-id="53e19-145">MOF encryption</span></span>

- <span data-ttu-id="53e19-146">ведение журнала событий.</span><span class="sxs-lookup"><span data-stu-id="53e19-146">Event logging</span></span>

- <span data-ttu-id="53e19-147">Отчеты DSC службы автоматизации Azure</span><span class="sxs-lookup"><span data-stu-id="53e19-147">Azure Automation DSC reporting</span></span>

- <span data-ttu-id="53e19-148">Полнофункциональные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="53e19-148">Resources that are fully functional</span></span>

  - <span data-ttu-id="53e19-149">**Архив**</span><span class="sxs-lookup"><span data-stu-id="53e19-149">**Archive**</span></span>
  - <span data-ttu-id="53e19-150">**Среда**</span><span class="sxs-lookup"><span data-stu-id="53e19-150">**Environment**</span></span>
  - <span data-ttu-id="53e19-151">**Файл**</span><span class="sxs-lookup"><span data-stu-id="53e19-151">**File**</span></span>
  - <span data-ttu-id="53e19-152">**Журнал**</span><span class="sxs-lookup"><span data-stu-id="53e19-152">**Log**</span></span>
  - <span data-ttu-id="53e19-153">**ProcessSet**</span><span class="sxs-lookup"><span data-stu-id="53e19-153">**ProcessSet**</span></span>
  - <span data-ttu-id="53e19-154">**Реестр**</span><span class="sxs-lookup"><span data-stu-id="53e19-154">**Registry**</span></span>
  - <span data-ttu-id="53e19-155">**Сценарий**</span><span class="sxs-lookup"><span data-stu-id="53e19-155">**Script**</span></span>
  - <span data-ttu-id="53e19-156">**WindowsPackageCab**</span><span class="sxs-lookup"><span data-stu-id="53e19-156">**WindowsPackageCab**</span></span>
  - <span data-ttu-id="53e19-157">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="53e19-157">**WindowsProcess**</span></span>
  - <span data-ttu-id="53e19-158">**WaitForAll** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="53e19-158">**WaitForAll** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
  - <span data-ttu-id="53e19-159">**WaitForAny** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="53e19-159">**WaitForAny** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
  - <span data-ttu-id="53e19-160">**WaitForSome** (см. раздел [Указание межузловых зависимостей](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="53e19-160">**WaitForSome** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>

- <span data-ttu-id="53e19-161">Ресурсы, функциональность которых не полная.</span><span class="sxs-lookup"><span data-stu-id="53e19-161">Resources that are partially functional</span></span>

  - <span data-ttu-id="53e19-162">**Группа**</span><span class="sxs-lookup"><span data-stu-id="53e19-162">**Group**</span></span>
  - <span data-ttu-id="53e19-163">**GroupSet**</span><span class="sxs-lookup"><span data-stu-id="53e19-163">**GroupSet**</span></span>

    <span data-ttu-id="53e19-164">**Проблема**. Приведенные выше ресурсы не работают, если определенный экземпляр вызывается дважды (дважды запускается одна и та же конфигурация).</span><span class="sxs-lookup"><span data-stu-id="53e19-164">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>

  - <span data-ttu-id="53e19-165">**Служба**</span><span class="sxs-lookup"><span data-stu-id="53e19-165">**Service**</span></span>
  - <span data-ttu-id="53e19-166">**ServiceSet**</span><span class="sxs-lookup"><span data-stu-id="53e19-166">**ServiceSet**</span></span>

    <span data-ttu-id="53e19-167">**Проблема**. Работает только для запуска или остановки службы (атрибут status).</span><span class="sxs-lookup"><span data-stu-id="53e19-167">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="53e19-168">Не работает при попытке изменить другие атрибуты службы, например startuptype, credentials, description и т. д.</span><span class="sxs-lookup"><span data-stu-id="53e19-168">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="53e19-169">Возникает ошибка такого вида.</span><span class="sxs-lookup"><span data-stu-id="53e19-169">The error thrown is similar to:</span></span>

    ```
    Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.
    ```

- <span data-ttu-id="53e19-170">Нефункционирующие ресурсы.</span><span class="sxs-lookup"><span data-stu-id="53e19-170">Resources that are not functional</span></span>

  - <span data-ttu-id="53e19-171">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="53e19-171">**User**</span></span>

## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="53e19-172">Функции DSC, недоступные на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="53e19-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="53e19-173">Следующие функции DSC в настоящее время недоступны для Nano Server:</span><span class="sxs-lookup"><span data-stu-id="53e19-173">The following DSC features are not currently available on Nano Server:</span></span>

- <span data-ttu-id="53e19-174">Расшифровка документа MOF с помощью зашифрованных паролей.</span><span class="sxs-lookup"><span data-stu-id="53e19-174">Decrypting MOF document with encrypted password(s)</span></span>
- <span data-ttu-id="53e19-175">Опрашивающий сервер — в настоящее время опрашивающий сервер нельзя настроить на сервере Nano Server.</span><span class="sxs-lookup"><span data-stu-id="53e19-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
- <span data-ttu-id="53e19-176">Все компоненты, не указанные в списке функций, работают.</span><span class="sxs-lookup"><span data-stu-id="53e19-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="53e19-177">Использование настраиваемых ресурсов DSC на сервере Nano Server</span><span class="sxs-lookup"><span data-stu-id="53e19-177">Using custom DSC resources on Nano Server</span></span>

<span data-ttu-id="53e19-178">Поскольку набор API Windows и библиотек CLR, доступный на сервере Nano Server, ограничен, ресурсы DSC, работающие в полной версии среды выполнения Windows, не всегда работают в Nano Server.</span><span class="sxs-lookup"><span data-stu-id="53e19-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span>
<span data-ttu-id="53e19-179">Перед развертыванием каких-либо настраиваемых ресурсов DSC в рабочей среде рекомендуется выполнять их полное и всестороннее тестирование.</span><span class="sxs-lookup"><span data-stu-id="53e19-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="53e19-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="53e19-180">See Also</span></span>

- [<span data-ttu-id="53e19-181">Начало работы с сервером Nano Server</span><span class="sxs-lookup"><span data-stu-id="53e19-181">Getting Started with Nano Server</span></span>](/windows-server/get-started/getting-started-with-nano-server)
