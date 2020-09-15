---
ms.date: 02/03/2020
keywords: powershell,core
title: Критические изменения в PowerShell Core 6.0
ms.openlocfilehash: 9ead635232930598634141369fd2cc299f0b1799
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86158196"
---
# <a name="breaking-changes-for-powershell-6x"></a><span data-ttu-id="3cd90-103">Критические изменения в PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="3cd90-103">Breaking Changes for PowerShell 6.x</span></span>

## <a name="features-no-longer-available-in-powershell-core"></a><span data-ttu-id="3cd90-104">Функции, которые больше недоступны в PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="3cd90-104">Features no longer available in PowerShell Core</span></span>

### <a name="modules-not-shipped-for-powershell-6x"></a><span data-ttu-id="3cd90-105">Модули, не поставляемые для PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="3cd90-105">Modules not shipped for PowerShell 6.x</span></span>

<span data-ttu-id="3cd90-106">По различным причинам совместимости следующие модули не включены в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3cd90-106">For various compatibility reasons, the following modules are not included in PowerShell 6.</span></span>

- <span data-ttu-id="3cd90-107">ISE</span><span class="sxs-lookup"><span data-stu-id="3cd90-107">ISE</span></span>
- <span data-ttu-id="3cd90-108">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="3cd90-108">Microsoft.PowerShell.LocalAccounts</span></span>
- <span data-ttu-id="3cd90-109">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="3cd90-109">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="3cd90-110">Microsoft.PowerShell.Operation.Validation</span><span class="sxs-lookup"><span data-stu-id="3cd90-110">Microsoft.PowerShell.Operation.Validation</span></span>
- <span data-ttu-id="3cd90-111">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3cd90-111">PSScheduledJob</span></span>
- <span data-ttu-id="3cd90-112">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="3cd90-112">PSWorkflow</span></span>
- <span data-ttu-id="3cd90-113">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="3cd90-113">PSWorkflowUtility</span></span>

### <a name="powershell-workflow"></a><span data-ttu-id="3cd90-114">Рабочий процесс PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cd90-114">PowerShell Workflow</span></span>

<span data-ttu-id="3cd90-115">[Рабочий процесс PowerShell][workflow] — это компонент Windows PowerShell на основе [Windows Workflow Foundation (WF)][workflow-foundation]. Он позволяет создавать надежные модули Runbook для долго выполняющихся или параллелизованных задач.</span><span class="sxs-lookup"><span data-stu-id="3cd90-115">[PowerShell Workflow][workflow] is a feature in Windows PowerShell that builds on top of [Windows Workflow Foundation (WF)][workflow-foundation] that enables the creation of robust runbooks for long-running or parallelized tasks.</span></span>

<span data-ttu-id="3cd90-116">Из-за отсутствия поддержки Windows Workflow Foundation в .NET Core мы больше не поддерживаем рабочий процесс PowerShell в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="3cd90-116">Due to the lack of support for Windows Workflow Foundation in .NET Core, we are not supporting PowerShell Workflow in PowerShell Core.</span></span>

<span data-ttu-id="3cd90-117">В будущем мы хотели бы реализовать собственный параллелизм в языке PowerShell без необходимости использовать рабочий процесс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cd90-117">In the future, we would like to enable native parallelism/concurrency in the PowerShell language without the need for PowerShell Workflow.</span></span>

<span data-ttu-id="3cd90-118">Если нужно возобновить выполнение скрипта после перезагрузки операционной системы с помощью контрольных точек, рекомендуем использовать планировщик задач. Он позволит запустить скрипт при запуске ОС. Но скрипт должен поддерживать свое собственное состояние (например, сохранять его в файле).</span><span class="sxs-lookup"><span data-stu-id="3cd90-118">If there is a need to use checkpoints to resume a script after the OS restarts, we recommend using Task Scheduler to run a script on OS startup, but the script would need to maintain its own state (like persisting it to a file).</span></span>

[workflow]: /previous-versions/powershell/scripting/components/workflows-guide
[workflow-foundation]: /dotnet/framework/windows-workflow-foundation/

### <a name="custom-snap-ins"></a><span data-ttu-id="3cd90-119">Настраиваемые оснастки</span><span class="sxs-lookup"><span data-stu-id="3cd90-119">Custom snap-ins</span></span>

<span data-ttu-id="3cd90-120">[Оснастки PowerShell][snapin] являются предшественниками модулей PowerShell, которые не имеют широкого распространения в сообществе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cd90-120">[PowerShell snap-ins][snapin] are a predecessor to PowerShell modules that do not have widespread adoption in the PowerShell community.</span></span>

<span data-ttu-id="3cd90-121">Из-за сложности поддержки оснасток и отсутствия их использования в сообществе мы больше не поддерживаем настраиваемые оснастки в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="3cd90-121">Due to the complexity of supporting snap-ins and their lack of usage in the community, we no longer support custom snap-ins in PowerShell Core.</span></span>

<span data-ttu-id="3cd90-122">В настоящее время это нарушает работу модулей `ActiveDirectory` и `DnsClient` в Windows и Windows Server.</span><span class="sxs-lookup"><span data-stu-id="3cd90-122">Today, this breaks the `ActiveDirectory` and `DnsClient` modules in Windows and Windows Server.</span></span>

[snapin]: /powershell/module/microsoft.powershell.core/about/about_pssnapins

### <a name="wmi-v1-cmdlets"></a><span data-ttu-id="3cd90-123">Командлеты инструментария WMI версии 1</span><span class="sxs-lookup"><span data-stu-id="3cd90-123">WMI v1 cmdlets</span></span>

<span data-ttu-id="3cd90-124">Из-за сложности поддержки двух наборов модулей на основе инструментария WMI мы удалили командлеты инструментария WMI версии 1 из PowerShell Core:</span><span class="sxs-lookup"><span data-stu-id="3cd90-124">Due to the complexity of supporting two sets of WMI-based modules, we removed the WMI v1 cmdlets from PowerShell Core:</span></span>

- `Register-WmiEvent`
- `Set-WmiInstance`
- `Invoke-WmiMethod`
- `Get-WmiObject`
- `Remove-WmiObject`

<span data-ttu-id="3cd90-125">Вместо этого мы рекомендуем вам использовать командлеты CIM (также называемыми инструментарием WMI версии 2), которые обеспечивают те же функциональные возможности, а также новые возможности и обновленный синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3cd90-125">Instead, we recommend that you the use the CIM (aka WMI v2) cmdlets which provide the same functionality with new functionality and a redesigned syntax:</span></span>

- `Get-CimAssociatedInstance`
- `Get-CimClass`
- `Get-CimInstance`
- `Get-CimSession`
- `Invoke-CimMethod`
- `New-CimInstance`
- `New-CimSession`
- `New-CimSessionOption`
- `Register-CimIndicationEvent`
- `Remove-CimInstance`
- `Remove-CimSession`
- `Set-CimInstance`

### <a name="microsoftpowershelllocalaccounts"></a><span data-ttu-id="3cd90-126">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="3cd90-126">Microsoft.PowerShell.LocalAccounts</span></span>

<span data-ttu-id="3cd90-127">Из-за использования неподдерживаемых API модуль `Microsoft.PowerShell.LocalAccounts` был удален из PowerShell Core, пока не будет найдено лучшее решение.</span><span class="sxs-lookup"><span data-stu-id="3cd90-127">Due to the use of unsupported APIs, `Microsoft.PowerShell.LocalAccounts` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="new-webserviceproxy-cmdlet-removed"></a><span data-ttu-id="3cd90-128">Командлет `New-WebServiceProxy` удален</span><span class="sxs-lookup"><span data-stu-id="3cd90-128">`New-WebServiceProxy` cmdlet removed</span></span>

<span data-ttu-id="3cd90-129">.NET Core не поддерживает платформу Windows Communication Framework, которая предоставляет службы для использования протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="3cd90-129">.NET Core does not support the Windows Communication Framework, which provide services for using the SOAP protocol.</span></span> <span data-ttu-id="3cd90-130">Этот командлет удален, так как для него нужен протокол SOAP.</span><span class="sxs-lookup"><span data-stu-id="3cd90-130">This cmdlet was removed because it requires SOAP.</span></span>

### <a name="-transaction-cmdlets-removed"></a><span data-ttu-id="3cd90-131">`*-Transaction` командлеты удалены</span><span class="sxs-lookup"><span data-stu-id="3cd90-131">`*-Transaction` cmdlets removed</span></span>

<span data-ttu-id="3cd90-132">Эти командлеты использовали очень ограниченный объем использования.</span><span class="sxs-lookup"><span data-stu-id="3cd90-132">These cmdlets had very limited usage.</span></span> <span data-ttu-id="3cd90-133">Было принято решение о прекращении их поддержки.</span><span class="sxs-lookup"><span data-stu-id="3cd90-133">The decision was made to discontinue support for them.</span></span>

- `Complete-Transaction`
- `Get-Transaction`
- `Start-Transaction`
- `Undo-Transaction`
- `Use-Transaction`

### <a name="security-cmdlets-not-available-on-non-windows-platforms"></a><span data-ttu-id="3cd90-134">Командлеты безопасности недоступны на платформах, отличных от Windows</span><span class="sxs-lookup"><span data-stu-id="3cd90-134">Security cmdlets not available on non-Windows platforms</span></span>

- `Get-Acl`
- `Set-Acl`
- `Get-AuthenticodeSignature`
- `Set-AuthenticodeSignature`
- `Get-CmsMessage`
- `Protect-CmsMessage`
- `Unprotect-CmsMessage`
- `New-FileCatalog`
- `Test-FileCatalog`

### <a name="-computerand-other-windows-specific-cmdlets"></a><span data-ttu-id="3cd90-135">`*-Computer`и другие командлеты для Windows</span><span class="sxs-lookup"><span data-stu-id="3cd90-135">`*-Computer`and other Windows-specific cmdlets</span></span>

<span data-ttu-id="3cd90-136">Из-за использования неподдерживаемых API следующие командлеты исключены из PowerShell Core, пока не будет найдено лучшее решение.</span><span class="sxs-lookup"><span data-stu-id="3cd90-136">Due to the use of unsupported APIs, the following cmdlets have been removed from PowerShell Core until a better solution is found.</span></span>

- `Get-Clipboard`
- `Set-Clipboard`
- `Add-Computer`
- `Checkpoint-Computer`
- `Remove-Computer`
- `Restore-Computer`
- `Reset-ComputerMachinePassword`
- `Disable-ComputerRestore`
- `Enable-ComputerRestore`
- `Get-ComputerRestorePoint`
- `Test-ComputerSecureChannel`
- `Get-ControlPanelItem`
- `Show-ControlPanelItem`
- `Get-HotFix`
- `Clear-RecycleBin`
- `Update-List`
- `Out-Printer`
- `ConvertFrom-String`
- `Convert-String`

### <a name="-counter-cmdlets"></a><span data-ttu-id="3cd90-137">Командлеты `*-Counter`</span><span class="sxs-lookup"><span data-stu-id="3cd90-137">`*-Counter` cmdlets</span></span>

<span data-ttu-id="3cd90-138">Из-за использования неподдерживаемых API модуль `*-Counter` был удален из PowerShell Core, пока не будет найдено лучшее решение.</span><span class="sxs-lookup"><span data-stu-id="3cd90-138">Due to the use of unsupported APIs, the `*-Counter` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="-eventlog-cmdlets"></a><span data-ttu-id="3cd90-139">Командлеты `*-EventLog`</span><span class="sxs-lookup"><span data-stu-id="3cd90-139">`*-EventLog` cmdlets</span></span>

<span data-ttu-id="3cd90-140">Из-за использования неподдерживаемых API модуль `*-EventLog` был удален из PowerShell Core,</span><span class="sxs-lookup"><span data-stu-id="3cd90-140">Due to the use of unsupported APIs, the `*-EventLog` has been removed from PowerShell Core.</span></span> <span data-ttu-id="3cd90-141">пока не будет найдено лучшее решение.</span><span class="sxs-lookup"><span data-stu-id="3cd90-141">until a better solution is found.</span></span> <span data-ttu-id="3cd90-142">`Get-WinEvent` и `Create-WinEvent` доступны для получения и создания событий в Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd90-142">`Get-WinEvent` and `Create-WinEvent` are available to get and create events on Windows.</span></span>

### <a name="cmdlets-that-use-wpf-removed"></a><span data-ttu-id="3cd90-143">Командлеты, использующие WPF, удалены</span><span class="sxs-lookup"><span data-stu-id="3cd90-143">Cmdlets that use WPF removed</span></span>

<span data-ttu-id="3cd90-144">Платформа Windows Presentation Framework не поддерживается в CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3cd90-144">The Windows Presentation Framework is not supported on CoreCLR.</span></span> <span data-ttu-id="3cd90-145">Затрагиваются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="3cd90-145">The following cmdlets are affected:</span></span>

- `Show-Command`
- `Out-GridView`
- <span data-ttu-id="3cd90-146">Параметр **showwindow** для `Get-Help`</span><span class="sxs-lookup"><span data-stu-id="3cd90-146">The **showwindow** parameter of `Get-Help`</span></span>

### <a name="some-dsc-cmdlets-removed"></a><span data-ttu-id="3cd90-147">Некоторые командлеты DSC удалены</span><span class="sxs-lookup"><span data-stu-id="3cd90-147">Some DSC cmdlets removed</span></span>

- `Get-DscConfiguration`
- `Publish-DscConfiguration`
- `Restore-DscConfiguration`
- `Start-DscConfiguration`
- `Stop-DscConfiguration`
- `Test-DscConfiguration`
- `Update-DscConfiguration`
- `Remove-DscConfigurationDocument`
- `Get-DscConfigurationStatus`
- `Disable-DscDebug`
- `Enable-DscDebug`
- `Get-DscLocalConfigurationManager`
- `Set-DscLocalConfigurationManager`
- `Invoke-DscResource`

## <a name="enginelanguage-changes"></a><span data-ttu-id="3cd90-148">Изменения модуля и языка</span><span class="sxs-lookup"><span data-stu-id="3cd90-148">Engine/language changes</span></span>

### <a name="rename-powershellexe-to-pwshexe-5101"></a><span data-ttu-id="3cd90-149">`powershell.exe` переименован в `pwsh.exe` [№ 5101](https://github.com/PowerShell/PowerShell/issues/5101)</span><span class="sxs-lookup"><span data-stu-id="3cd90-149">Rename `powershell.exe` to `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span></span>

<span data-ttu-id="3cd90-150">Чтобы предоставить пользователям детерминированный способ вызова PowerShell Core в Windows (в отличие от Windows PowerShell), двоичный файл PowerShell Core был переименован в `pwsh.exe` на платформах Windows и в `pwsh` на других платформах.</span><span class="sxs-lookup"><span data-stu-id="3cd90-150">In order to give users a deterministic way to call PowerShell Core on Windows (as opposed to Windows PowerShell), the PowerShell Core binary was changed to `pwsh.exe` on Windows and `pwsh` on non-Windows platforms.</span></span>

<span data-ttu-id="3cd90-151">Сокращенное имя также согласуется с именованием оболочек на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd90-151">The shortened name is also consistent with naming of shells on non-Windows platforms.</span></span>

### <a name="dont-insert-line-breaks-to-output-except-for-tables-5193"></a><span data-ttu-id="3cd90-152">Разрывы строк не вставляются в выходные данные (за исключением таблиц) [№ 5193](https://github.com/PowerShell/PowerShell/issues/5193)</span><span class="sxs-lookup"><span data-stu-id="3cd90-152">Don't insert line breaks to output (except for tables) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span></span>

<span data-ttu-id="3cd90-153">Раньше выходные данные выравнивались по ширине консоли, а разрывы строк добавлялись в конце окна консоли. Из-за этого выходные данные не были переформатированы как ожидалось, если размер терминала был изменен.</span><span class="sxs-lookup"><span data-stu-id="3cd90-153">Previously, output was aligned to the width of the console and line breaks were added at the end width of the console, meaning the output didn't get reformatted as expected if the terminal was resized.</span></span> <span data-ttu-id="3cd90-154">Это изменение не было применено к таблицам, так как разрывы строк необходимы для выравнивания столбцов.</span><span class="sxs-lookup"><span data-stu-id="3cd90-154">This change was not applied to tables, as the line breaks are necessary to keep the columns aligned.</span></span>

### <a name="skip-null-element-check-for-collections-with-a-value-type-element-type-5432"></a><span data-ttu-id="3cd90-155">Пропуск проверки элемента NULL для коллекций с типом элемента в виде типа значения [№ 5432](https://github.com/PowerShell/PowerShell/issues/5432)</span><span class="sxs-lookup"><span data-stu-id="3cd90-155">Skip null-element check for collections with a value-type element type [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span></span>

<span data-ttu-id="3cd90-156">Для параметра `Mandatory` и атрибутов `ValidateNotNull` и `ValidateNotNullOrEmpty` пропускается проверка элемента NULL, если тип элемента коллекции является типом значения.</span><span class="sxs-lookup"><span data-stu-id="3cd90-156">For the `Mandatory` parameter and `ValidateNotNull` and `ValidateNotNullOrEmpty` attributes, skip the null-element check if the collection's element type is value type.</span></span>

### <a name="change-outputencoding-to-use-utf-8-nobom-encoding-rather-than-ascii-5369"></a><span data-ttu-id="3cd90-157">Теперь `$OutputEncoding` использует кодирование `UTF-8 NoBOM`, а не ASCII [№ 5369](https://github.com/PowerShell/PowerShell/issues/5369)</span><span class="sxs-lookup"><span data-stu-id="3cd90-157">Change `$OutputEncoding` to use `UTF-8 NoBOM` encoding rather than ASCII [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span></span>

<span data-ttu-id="3cd90-158">Предыдущая кодировка, ASCII (7 бит), в некоторых случаях приводила к неправильному изменению выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3cd90-158">The previous encoding, ASCII (7-bit), would result in incorrect alteration of the output in some cases.</span></span> <span data-ttu-id="3cd90-159">С этим изменением `UTF-8 NoBOM` становится кодировкой по умолчанию, благодаря чему выходные данные в Юникоде остаются в кодировке, поддерживаемой большинством инструментов и операционных систем.</span><span class="sxs-lookup"><span data-stu-id="3cd90-159">This change is to make `UTF-8 NoBOM` default, which preserves Unicode output with an encoding supported by most tools and operating systems.</span></span>

### <a name="remove-allscope-from-most-default-aliases-5268"></a><span data-ttu-id="3cd90-160">Атрибут `AllScope` удален из большинства псевдонимов по умолчанию [№ 5268](https://github.com/PowerShell/PowerShell/issues/5268)</span><span class="sxs-lookup"><span data-stu-id="3cd90-160">Remove `AllScope` from most default aliases [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span></span>

<span data-ttu-id="3cd90-161">Чтобы ускорить создание области, атрибут `AllScope` был удален из большинства псевдонимов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cd90-161">To speed up scope creation, `AllScope` was removed from most default aliases.</span></span> <span data-ttu-id="3cd90-162">Атрибут `AllScope` был оставлен для нескольких часто используемых псевдонимов, где поиск выполнялся быстрее.</span><span class="sxs-lookup"><span data-stu-id="3cd90-162">`AllScope` was left for a few frequently used aliases where the lookup was faster.</span></span>

### <a name="-verbose-and--debug-no-longer-overrides-erroractionpreference-5113"></a><span data-ttu-id="3cd90-163">`-Verbose` и `-Debug` больше не переопределяют `$ErrorActionPreference` [№ 5113](https://github.com/PowerShell/PowerShell/issues/5113)</span><span class="sxs-lookup"><span data-stu-id="3cd90-163">`-Verbose` and `-Debug` no longer overrides `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span></span>

<span data-ttu-id="3cd90-164">Ранее, если `-Verbose` или `-Debug` были указаны, поведение `$ErrorActionPreference` переопределялось.</span><span class="sxs-lookup"><span data-stu-id="3cd90-164">Previously, if `-Verbose` or `-Debug` were specified, it overrode the behavior of `$ErrorActionPreference`.</span></span> <span data-ttu-id="3cd90-165">С этим изменением `-Verbose` и `-Debug` больше не влияют на поведение `$ErrorActionPreference`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-165">With this change, `-Verbose` and `-Debug` no longer affect the behavior of `$ErrorActionPreference`.</span></span>

## <a name="cmdlet-changes"></a><span data-ttu-id="3cd90-166">Изменения в командлетах</span><span class="sxs-lookup"><span data-stu-id="3cd90-166">Cmdlet changes</span></span>

### <a name="invoke-restmethod-doesnt-return-useful-info-when-no-data-is-returned-5320"></a><span data-ttu-id="3cd90-167">Invoke-RestMethod не возвращает полезные сведения, если данные не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="3cd90-167">Invoke-RestMethod doesn't return useful info when no data is returned.</span></span> [<span data-ttu-id="3cd90-168">№ 5320</span><span class="sxs-lookup"><span data-stu-id="3cd90-168">#5320</span></span>](https://github.com/PowerShell/PowerShell/issues/5320)

<span data-ttu-id="3cd90-169">Если API возвращал только значение `null`, Invoke-RestMethod сериализовал его в качестве строки `"null"`, а не `$null`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-169">When an API returns just `null`, Invoke-RestMethod was serializing this as the string `"null"` instead of `$null`.</span></span> <span data-ttu-id="3cd90-170">Это изменение исправляет логику в `Invoke-RestMethod`, чтобы надлежащим образом сериализовать одно допустимое значение литерала JSON `null` как `$null`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-170">This change fixes the logic in `Invoke-RestMethod` to properly serialize a valid single value JSON `null` literal as `$null`.</span></span>

### <a name="remove--protocol-from--computer-cmdlets-5277"></a><span data-ttu-id="3cd90-171">Параметр `-Protocol` удален из командлетов `*-Computer`[№ 5277](https://github.com/PowerShell/PowerShell/issues/5277)</span><span class="sxs-lookup"><span data-stu-id="3cd90-171">Remove `-Protocol` from `*-Computer` cmdlets [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span></span>

<span data-ttu-id="3cd90-172">Из-за проблем с удаленным взаимодействием RPC в CoreFX (особенно на платформах не под управлением Windows) и обеспечением согласованного удаленного взаимодействия в PowerShell параметр `-Protocol` был удален из командлетов `\*-Computer`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-172">Due to issues with RPC remoting in CoreFX (particularly on non-Windows platforms) and ensuring a consistent remoting experience in PowerShell, the `-Protocol` parameter was removed from the `\*-Computer` cmdlets.</span></span> <span data-ttu-id="3cd90-173">DCOM больше не поддерживается для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3cd90-173">DCOM is no longer supported for remoting.</span></span> <span data-ttu-id="3cd90-174">Следующие командлеты поддерживают только удаленное взаимодействие через WSMAN.</span><span class="sxs-lookup"><span data-stu-id="3cd90-174">The following cmdlets only support WSMAN remoting:</span></span>

- <span data-ttu-id="3cd90-175">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="3cd90-175">Rename-Computer</span></span>
- <span data-ttu-id="3cd90-176">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3cd90-176">Restart-Computer</span></span>
- <span data-ttu-id="3cd90-177">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="3cd90-177">Stop-Computer</span></span>

### <a name="remove--computername-from--service-cmdlets-5090"></a><span data-ttu-id="3cd90-178">Параметр `-ComputerName` удален из командлетов `*-Service`[№ 5090](https://github.com/PowerShell/PowerShell/issues/5094)</span><span class="sxs-lookup"><span data-stu-id="3cd90-178">Remove `-ComputerName` from `*-Service` cmdlets [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span></span>

<span data-ttu-id="3cd90-179">Чтобы способствовать согласованному использованию PSRP, параметр `-ComputerName` был удален из командлетов `*-Service`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-179">In order to encourage the consistent use of PSRP, the `-ComputerName` parameter was removed from `*-Service` cmdlets.</span></span>

### <a name="fix-get-item--literalpath-ab-if-ab-doesnt-actually-exist-to-return-error-5197"></a><span data-ttu-id="3cd90-180">Теперь при обработке `Get-Item -LiteralPath a*b` возвращается ошибка, если `a*b` фактически не существует [№ 5197](https://github.com/PowerShell/PowerShell/issues/5197)</span><span class="sxs-lookup"><span data-stu-id="3cd90-180">Fix `Get-Item -LiteralPath a*b` if `a*b` doesn't actually exist to return error [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span></span>

<span data-ttu-id="3cd90-181">Раньше при указании подстановочного знака `-LiteralPath` обрабатывал его так же, как `-Path`, и если для подстановочного знака не было найдено файлов, автоматически выполнялся выход.</span><span class="sxs-lookup"><span data-stu-id="3cd90-181">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="3cd90-182">Правильное поведение — `-LiteralPath` является литералом, поэтому, если файл не существует, должна возвращаться ошибка.</span><span class="sxs-lookup"><span data-stu-id="3cd90-182">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="3cd90-183">С этим изменением подстановочные знаки, используемые с `-Literal`, рассматриваются в качестве литерала.</span><span class="sxs-lookup"><span data-stu-id="3cd90-183">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="import-csv-should-apply-pstypenames-upon-import-when-type-information-is-present-in-the-csv-5134"></a><span data-ttu-id="3cd90-184">`Import-Csv` применяет `PSTypeNames` при импорте, если информация о типе присутствует в CSV [№ 5134](https://github.com/PowerShell/PowerShell/issues/5134)</span><span class="sxs-lookup"><span data-stu-id="3cd90-184">`Import-Csv` should apply `PSTypeNames` upon import when type information is present in the CSV [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span></span>

<span data-ttu-id="3cd90-185">Ранее объекты, экспортированные с помощью `Export-CSV` с информацией `TypeInformation`, импортированной с помощью `ConvertFrom-Csv`, не сохраняли информацию о типе.</span><span class="sxs-lookup"><span data-stu-id="3cd90-185">Previously, objects exported using `Export-CSV` with `TypeInformation` imported with `ConvertFrom-Csv` were not retaining the type information.</span></span> <span data-ttu-id="3cd90-186">Это изменение добавляет информацию о типе в элемент `PSTypeNames`, если она доступна в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="3cd90-186">This change adds the type information to `PSTypeNames` member if available from the CSV file.</span></span>

### <a name="-notypeinformation-should-be-default-on-export-csv-5131"></a><span data-ttu-id="3cd90-187">`-NoTypeInformation` теперь присутствует по умолчанию в `Export-Csv` [№ 5131](https://github.com/PowerShell/PowerShell/issues/5131)</span><span class="sxs-lookup"><span data-stu-id="3cd90-187">`-NoTypeInformation` should be default on `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span></span>

<span data-ttu-id="3cd90-188">Это изменение было внесено с учетом отзывов пользователей о том, чтобы `Export-CSV` по умолчанию содержал сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="3cd90-188">This change was made to address customer feedback on the default behavior of `Export-CSV` to include type information.</span></span>

<span data-ttu-id="3cd90-189">Ранее командлет выводил комментарий в качестве первой строки, содержащей имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="3cd90-189">Previously, the cmdlet would output a comment as the first line containing the type name of the object.</span></span> <span data-ttu-id="3cd90-190">Изменение заключается в том, чтобы подавить это поведение по умолчанию, так как оно не распознается большинством инструментов.</span><span class="sxs-lookup"><span data-stu-id="3cd90-190">The change is to suppress this by default as it's not understood by most tools.</span></span> <span data-ttu-id="3cd90-191">Используйте `-IncludeTypeInformation`, чтобы сохранить предыдущий режим работы.</span><span class="sxs-lookup"><span data-stu-id="3cd90-191">Use `-IncludeTypeInformation` to retain the previous behavior.</span></span>

### <a name="web-cmdlets-should-warn-when--credential-is-sent-over-unencrypted-connections-5112"></a><span data-ttu-id="3cd90-192">Теперь веб-командлеты выдают предупреждение, если `-Credential` отправляется по незашифрованным подключениям [№ 5112](https://github.com/PowerShell/PowerShell/issues/5112)</span><span class="sxs-lookup"><span data-stu-id="3cd90-192">Web Cmdlets should warn when `-Credential` is sent over unencrypted connections [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span></span>

<span data-ttu-id="3cd90-193">При использовании HTTP содержимое, включая пароли, отправляется в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="3cd90-193">When using HTTP, content including passwords are sent as clear-text.</span></span> <span data-ttu-id="3cd90-194">В этом изменении такое поведение запрещено по умолчанию и возвращается ошибка, если учетные данные передаются небезопасным образом.</span><span class="sxs-lookup"><span data-stu-id="3cd90-194">This change is to not allow this by default and return an error if credentials are being passed in an insecure manner.</span></span> <span data-ttu-id="3cd90-195">Пользователи могут обойти это с помощью параметра `-AllowUnencryptedAuthentication`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-195">Users can bypass this by using the `-AllowUnencryptedAuthentication` switch.</span></span>

## <a name="api-changes"></a><span data-ttu-id="3cd90-196">Изменения в API</span><span class="sxs-lookup"><span data-stu-id="3cd90-196">API changes</span></span>

### <a name="remove-addtypecommandbase-class-5407"></a><span data-ttu-id="3cd90-197">Удален класс `AddTypeCommandBase`[№ 5407](https://github.com/PowerShell/PowerShell/issues/5407)</span><span class="sxs-lookup"><span data-stu-id="3cd90-197">Remove `AddTypeCommandBase` class [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span></span>

<span data-ttu-id="3cd90-198">Класс `AddTypeCommandBase` был удален из `Add-Type` для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="3cd90-198">The `AddTypeCommandBase` class was removed from `Add-Type` to improve performance.</span></span> <span data-ttu-id="3cd90-199">Этот класс используется только командлетом Add-Type и не должен влиять на пользователей.</span><span class="sxs-lookup"><span data-stu-id="3cd90-199">This class is only used by the Add-Type cmdlet and should not impact users.</span></span>

### <a name="unify-cmdlets-with-parameter--encoding-to-be-of-type-systemtextencoding-5080"></a><span data-ttu-id="3cd90-200">Теперь командлеты с параметром `-Encoding` имеют тип `System.Text.Encoding` [№ 5080](https://github.com/PowerShell/PowerShell/issues/5080)</span><span class="sxs-lookup"><span data-stu-id="3cd90-200">Unify cmdlets with parameter `-Encoding` to be of type `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span></span>

<span data-ttu-id="3cd90-201">Значение `-Encoding``Byte` было удалено из командлетов поставщика файловой системы.</span><span class="sxs-lookup"><span data-stu-id="3cd90-201">The `-Encoding` value `Byte` has been removed from the filesystem provider cmdlets.</span></span> <span data-ttu-id="3cd90-202">Новый параметр, `-AsByteStream`, теперь используется для указания того, что в качестве входного потока требуется поток байтов или что выходной поток представляет собой поток байтов.</span><span class="sxs-lookup"><span data-stu-id="3cd90-202">A new parameter, `-AsByteStream`, is now used to specify that a byte stream is required as input or that the output is a stream of bytes.</span></span>

### <a name="add-better-error-message-for-empty-and-null--uformat-parameter-5055"></a><span data-ttu-id="3cd90-203">Добавлено улучшенное сообщение об ошибке для параметра `-UFormat` с пустым или нулевым значением [№ 5055](https://github.com/PowerShell/PowerShell/issues/5055)</span><span class="sxs-lookup"><span data-stu-id="3cd90-203">Add better error message for empty and null `-UFormat` parameter [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span></span>

<span data-ttu-id="3cd90-204">Ранее при передаче пустой строки формата в `-UFormat` отображалось бесполезное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="3cd90-204">Previously, when passing an empty format string to `-UFormat`, an unhelpful error message would appear.</span></span> <span data-ttu-id="3cd90-205">Было добавлено более описательное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="3cd90-205">A more descriptive error has been added.</span></span>

### <a name="clean-up-console-code-4995"></a><span data-ttu-id="3cd90-206">Очищен код консоли [№ 4995](https://github.com/PowerShell/PowerShell/issues/4995)</span><span class="sxs-lookup"><span data-stu-id="3cd90-206">Clean up console code [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span></span>

<span data-ttu-id="3cd90-207">Следующие функции были удалены, так как они не поддерживаются в PowerShell Core. Какие-либо планы по реализации их поддержки отсутствуют, так как они относятся к прежним версиям PowerShell. `-psconsolefile` — параметр и код, `-importsystemmodules` — параметр, код, а также код, изменяющий шрифт.</span><span class="sxs-lookup"><span data-stu-id="3cd90-207">The following features were removed as they are not supported in PowerShell Core, and there are no plans to add support as they exist for legacy reasons for Windows PowerShell: `-psconsolefile` switch and code, `-importsystemmodules` switch and code, and font changing code.</span></span>

### <a name="removed-runspaceconfiguration-support-4942"></a><span data-ttu-id="3cd90-208">Удалена поддержка `RunspaceConfiguration`[№ 4942](https://github.com/PowerShell/PowerShell/issues/4942)</span><span class="sxs-lookup"><span data-stu-id="3cd90-208">Removed `RunspaceConfiguration` support [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span></span>

<span data-ttu-id="3cd90-209">Ранее при создании пространства выполнения PowerShell программными средствами с помощью API можно было использовать прежние версии [`RunspaceConfiguration`][runspaceconfig] или более новые версии [`InitialSessionState`][iss].</span><span class="sxs-lookup"><span data-stu-id="3cd90-209">Previously, when creating a PowerShell runspace programmatically using the API you could use the legacy [`RunspaceConfiguration`][runspaceconfig] or the newer [`InitialSessionState`][iss].</span></span> <span data-ttu-id="3cd90-210">Это изменение удалило поддержку `RunspaceConfiguration`, и теперь поддерживается только `InitialSessionState`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-210">This change removed support for `RunspaceConfiguration` and only supports `InitialSessionState`.</span></span>

[runspaceconfig]: /dotnet/api/system.management.automation.runspaces.runspaceconfiguration
[iss]: /dotnet/api/system.management.automation.runspaces.initialsessionstate

### <a name="commandinvocationintrinsicsinvokescript-bind-arguments-to-input-instead-of-args-4923"></a><span data-ttu-id="3cd90-211">`CommandInvocationIntrinsics.InvokeScript` — привязка аргументов к `$input`, а не к `$args` [№ 4923](https://github.com/PowerShell/PowerShell/issues/4923)</span><span class="sxs-lookup"><span data-stu-id="3cd90-211">`CommandInvocationIntrinsics.InvokeScript` bind arguments to `$input` instead of `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span></span>

<span data-ttu-id="3cd90-212">Из-за неверного положения параметра аргументы передавались в качестве входных данных, а не аргументов.</span><span class="sxs-lookup"><span data-stu-id="3cd90-212">An incorrect position of a parameter resulted in the args passed as input instead of as args.</span></span>

### <a name="remove-unsupported--showwindow-switch-from-get-help-4903"></a><span data-ttu-id="3cd90-213">Удален неподдерживаемый параметр `-showwindow` из `Get-Help` [№ 4903](https://github.com/PowerShell/PowerShell/issues/4903)</span><span class="sxs-lookup"><span data-stu-id="3cd90-213">Remove unsupported `-showwindow` switch from `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span></span>

<span data-ttu-id="3cd90-214">`-showwindow` использует WPF, который не поддерживается в CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3cd90-214">`-showwindow` relies on WPF, which is not supported on CoreCLR.</span></span>

### <a name="allow--to-be-used-in-registry-path-for-remove-item-4866"></a><span data-ttu-id="3cd90-215">Разрешено использовать \* в пути реестра для `Remove-Item` [№ 4866](https://github.com/PowerShell/PowerShell/issues/4866)</span><span class="sxs-lookup"><span data-stu-id="3cd90-215">Allow \* to be used in registry path for `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span></span>

<span data-ttu-id="3cd90-216">Раньше при указании подстановочного знака `-LiteralPath` обрабатывал его так же, как `-Path`, и если для подстановочного знака не было найдено файлов, автоматически выполнялся выход.</span><span class="sxs-lookup"><span data-stu-id="3cd90-216">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="3cd90-217">Правильное поведение — `-LiteralPath` является литералом, поэтому, если файл не существует, должна возвращаться ошибка.</span><span class="sxs-lookup"><span data-stu-id="3cd90-217">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="3cd90-218">С этим изменением подстановочные знаки, используемые с `-Literal`, рассматриваются в качестве литерала.</span><span class="sxs-lookup"><span data-stu-id="3cd90-218">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="fix-set-service-failing-test-4802"></a><span data-ttu-id="3cd90-219">`Set-Service` исправлено для правильной обработки [№ 4802](https://github.com/PowerShell/PowerShell/issues/4802)</span><span class="sxs-lookup"><span data-stu-id="3cd90-219">Fix `Set-Service` failing test [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span></span>

<span data-ttu-id="3cd90-220">Ранее при использовании `New-Service -StartupType foo` часть `foo` игнорировалась и создавалась служба с определенным типом запуска по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cd90-220">Previously, if `New-Service -StartupType foo` was used, `foo` was ignored and the service was created with some default startup type.</span></span> <span data-ttu-id="3cd90-221">Это изменение предназначено, чтобы явно вызывать ошибку недопустимого типа запуска.</span><span class="sxs-lookup"><span data-stu-id="3cd90-221">This change is to explicitly throw an error for an invalid startup type.</span></span>

### <a name="rename-isosx-to-ismacos-4700"></a><span data-ttu-id="3cd90-222">`$IsOSX` переименован в `$IsMacOS` [№ 4700](https://github.com/PowerShell/PowerShell/issues/4700)</span><span class="sxs-lookup"><span data-stu-id="3cd90-222">Rename `$IsOSX` to `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span></span>

<span data-ttu-id="3cd90-223">Именование в PowerShell должно согласовываться с нашим именованием и соответствовать использованию в Apple ОС macOS вместо OSX.</span><span class="sxs-lookup"><span data-stu-id="3cd90-223">The naming in PowerShell should be consistent with our naming and conform to Apple's use of macOS instead of OSX.</span></span> <span data-ttu-id="3cd90-224">Однако для удобочитаемости и согласованности используется регистр Pascal.</span><span class="sxs-lookup"><span data-stu-id="3cd90-224">However, for readability and consistently we are staying with Pascal casing.</span></span>

### <a name="make-error-message-consistent-when-invalid-script-is-passed-to--file-better-error-when-passed-ambiguous-argument-4573"></a><span data-ttu-id="3cd90-225">Согласованное сообщение об ошибке при передаче недопустимого скрипта в -File, лучшая ошибка при передаче неоднозначного аргумента [№ 4573](https://github.com/PowerShell/PowerShell/issues/4573)</span><span class="sxs-lookup"><span data-stu-id="3cd90-225">Make error message consistent when invalid script is passed to -File, better error when passed ambiguous argument [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span></span>

<span data-ttu-id="3cd90-226">Коды выхода `pwsh.exe` изменены в соответствии с соглашениями Unix.</span><span class="sxs-lookup"><span data-stu-id="3cd90-226">Change the exit codes of `pwsh.exe` to align with Unix conventions</span></span>

### <a name="removal-of-localaccount-and-cmdlets-from--diagnostics-modules-4302-4303"></a><span data-ttu-id="3cd90-227">Модуль `LocalAccount` и командлеты удалены из модулей `Diagnostics`</span><span class="sxs-lookup"><span data-stu-id="3cd90-227">Removal of `LocalAccount` and cmdlets from  `Diagnostics` modules.</span></span> <span data-ttu-id="3cd90-228">[№ 4302](https://github.com/PowerShell/PowerShell/issues/4302) [№ 4303](https://github.com/PowerShell/PowerShell/issues/4303)</span><span class="sxs-lookup"><span data-stu-id="3cd90-228">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span></span>

<span data-ttu-id="3cd90-229">Из-за неподдерживаемых API модуль `LocalAccounts` и командлеты `Counter` в модуле `Diagnostics` были удалены, пока не будет найдено лучшее решение.</span><span class="sxs-lookup"><span data-stu-id="3cd90-229">Due to unsupported APIs, the `LocalAccounts` module and the `Counter` cmdlets in the `Diagnostics` module were removed until a better solution is found.</span></span>

### <a name="executing-powershell-script-with-bool-parameter-does-not-work-4036"></a><span data-ttu-id="3cd90-230">Выполнение скрипта PowerShell с параметром bool не работает [№ 4036](https://github.com/PowerShell/PowerShell/issues/4036)</span><span class="sxs-lookup"><span data-stu-id="3cd90-230">Executing PowerShell script with bool parameter does not work [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span></span>

<span data-ttu-id="3cd90-231">Ранее при использовании **powershell.exe** (теперь **pwsh.exe**) для выполнения скрипта PowerShell с параметром `-File` было невозможно передать значения `$true`/`$false` в качестве значений параметра.</span><span class="sxs-lookup"><span data-stu-id="3cd90-231">Previously, using **powershell.exe** (now **pwsh.exe**) to execute a PowerShell script using `-File` provided no way to pass `$true`/`$false` as parameter values.</span></span> <span data-ttu-id="3cd90-232">Была добавлена поддержка `$true`/`$false` в качестве анализируемых значений.</span><span class="sxs-lookup"><span data-stu-id="3cd90-232">Support for `$true`/`$false` as parsed values to parameters was added.</span></span> <span data-ttu-id="3cd90-233">Значения параметров также поддерживаются, так как в настоящий момент синтаксис документа не работает.</span><span class="sxs-lookup"><span data-stu-id="3cd90-233">Switch values are also supported as currently documented syntax doesn't work.</span></span>

### <a name="remove-clrversion-property-from-psversiontable-4027"></a><span data-ttu-id="3cd90-234">Свойство `ClrVersion` удалено из `$PSVersionTable` [№ 4027](https://github.com/PowerShell/PowerShell/issues/4027)</span><span class="sxs-lookup"><span data-stu-id="3cd90-234">Remove `ClrVersion` property from `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span></span>

<span data-ttu-id="3cd90-235">Свойство `ClrVersion` параметра `$PSVersionTable` бесполезно в CoreCLR. Пользователи не должны использовать это значение для определения совместимости.</span><span class="sxs-lookup"><span data-stu-id="3cd90-235">The `ClrVersion` property of `$PSVersionTable` is not useful with CoreCLR, end users should not be using that value to determine compatibility.</span></span>

### <a name="change-positional-parameter-for-powershellexe-from--command-to--file-4019"></a><span data-ttu-id="3cd90-236">Позиционный параметр для `powershell.exe` из `-Command` изменен на `-File` [№ 4019](https://github.com/PowerShell/PowerShell/issues/4019)</span><span class="sxs-lookup"><span data-stu-id="3cd90-236">Change positional parameter for `powershell.exe` from `-Command` to `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span></span>

<span data-ttu-id="3cd90-237">Разрешите использование знака решетки PowerShell на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd90-237">Enable shebang use of PowerShell on non-Windows platforms.</span></span> <span data-ttu-id="3cd90-238">В системах на основе Unix это означает, что вы можете создать исполняемый файл скрипта, который будет вызывать PowerShell автоматически, а не явно вызывать `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-238">This means on Unix based systems, you can make a script executable that would invoke PowerShell automatically rather than explicitly invoking `pwsh`.</span></span> <span data-ttu-id="3cd90-239">Это также означает, что вы можете выполнять такие команды, как `powershell foo.ps1` или `powershell fooScript`, без указания `-File`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-239">This also means that you can now do things like `powershell foo.ps1` or `powershell fooScript` without specifying `-File`.</span></span> <span data-ttu-id="3cd90-240">Однако это изменение требует явно указать `-c` или `-Command` при попытке запуска таких команд, как `powershell.exe Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-240">However, this change now requires that you explicitly specify `-c` or `-Command` when trying to do things like `powershell.exe Get-Command`.</span></span>

### <a name="implement-unicode-escape-parsing-3958"></a><span data-ttu-id="3cd90-241">Реализован анализ escape-символов в Юникоде [№ 3958](https://github.com/PowerShell/PowerShell/issues/3958)</span><span class="sxs-lookup"><span data-stu-id="3cd90-241">Implement Unicode escape parsing [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span></span>

<span data-ttu-id="3cd90-242">`` `u####`` или `` `u{####}`` преобразуются в соответствующий символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="3cd90-242">`` `u####`` or `` `u{####}`` is converted to the corresponding Unicode character.</span></span> <span data-ttu-id="3cd90-243">Для вывода литерала `` `u`` добавьте escape-символ в виде обратного апострофа: ``` ``u```.</span><span class="sxs-lookup"><span data-stu-id="3cd90-243">To output a literal `` `u``, escape the backtick: ``` ``u```.</span></span>

### <a name="change-new-modulemanifest-encoding-to-utf8nobom-on-non-windows-platforms-3940"></a><span data-ttu-id="3cd90-244">Кодирование `New-ModuleManifest` изменено на `UTF8NoBOM` на платформах, отличных от Windows [№ 3940](https://github.com/PowerShell/PowerShell/issues/3940)</span><span class="sxs-lookup"><span data-stu-id="3cd90-244">Change `New-ModuleManifest` encoding to `UTF8NoBOM` on non-Windows platforms [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span></span>

<span data-ttu-id="3cd90-245">Ранее `New-ModuleManifest` создавал манифесты PSD1 в UTF-16 с меткой порядка байтов, создавая проблемы для инструментов Linux.</span><span class="sxs-lookup"><span data-stu-id="3cd90-245">Previously, `New-ModuleManifest` creates psd1 manifests in UTF-16 with BOM, creating a problem for Linux tools.</span></span> <span data-ttu-id="3cd90-246">Это критическое изменение, которое изменяет кодировку `New-ModuleManifest` на UTF (без метки порядка байтов) в платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd90-246">This breaking change changes the encoding of `New-ModuleManifest` to be UTF (no BOM) in non-Windows platforms.</span></span>

### <a name="prevent-get-childitem-from-recursing-into-symlinks-1875-3780"></a><span data-ttu-id="3cd90-247">Предотвращение рекурсии `Get-ChildItem` в символические ссылки (№ 1875)</span><span class="sxs-lookup"><span data-stu-id="3cd90-247">Prevent `Get-ChildItem` from recursing into symlinks (#1875).</span></span> [<span data-ttu-id="3cd90-248">№ 3780</span><span class="sxs-lookup"><span data-stu-id="3cd90-248">#3780</span></span>](https://github.com/PowerShell/PowerShell/issues/3780)

<span data-ttu-id="3cd90-249">Это изменение приводит `Get-ChildItem` в соответствие с собственными командами `ls -r` Unix и `dir /s` Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd90-249">This change brings `Get-ChildItem` more in line with the Unix `ls -r` and the Windows `dir /s` native commands.</span></span> <span data-ttu-id="3cd90-250">Подобно упомянутым командам, командлет отображает символические ссылки на каталоги, найденные во время рекурсии, но не рекурсирует в них.</span><span class="sxs-lookup"><span data-stu-id="3cd90-250">Like the mentioned commands, the cmdlet displays symbolic links to directories found during recursion, but does not recurse into them.</span></span>

### <a name="fix-get-content--delimiter-to-not-include-the-delimiter-in-the-returned-lines-3706"></a><span data-ttu-id="3cd90-251">`Get-Content -Delimiter` исправлен таким образом, чтобы в возвращенных строках не содержался разделитель [№ 3706](https://github.com/PowerShell/PowerShell/issues/3706)</span><span class="sxs-lookup"><span data-stu-id="3cd90-251">Fix `Get-Content -Delimiter` to not include the delimiter in the returned lines [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span></span>

<span data-ttu-id="3cd90-252">Ранее при использовании `Get-Content -Delimiter` выходные данные были несогласованными и неудобными, так как для удаления разделителя требовалась их дальнейшая обработка.</span><span class="sxs-lookup"><span data-stu-id="3cd90-252">Previously, the output while using `Get-Content -Delimiter` was inconsistent and inconvenient as it required further processing of the data to remove the delimiter.</span></span> <span data-ttu-id="3cd90-253">Это изменение удаляет разделитель в возвращаемых строках.</span><span class="sxs-lookup"><span data-stu-id="3cd90-253">This change removes the delimiter in returned lines.</span></span>

### <a name="implement-format-hex-in-c-3320"></a><span data-ttu-id="3cd90-254">Реализация Format-Hex в C# [№ 3320](https://github.com/PowerShell/PowerShell/issues/3320)</span><span class="sxs-lookup"><span data-stu-id="3cd90-254">Implement Format-Hex in C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span></span>

<span data-ttu-id="3cd90-255">Параметр `-Raw` теперь не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="3cd90-255">The `-Raw` parameter is now a "no-op" (in that it does nothing).</span></span> <span data-ttu-id="3cd90-256">В дальнейшем все выходные данные будут отображаться с истинным представлением чисел, в том числе все байты для соответствующего типа (что параметр `-Raw` формально делал до этого изменения).</span><span class="sxs-lookup"><span data-stu-id="3cd90-256">Going forward all of the output will be displayed with a true representation of numbers that includes all of the bytes for its type (what the `-Raw` parameter was formally doing prior to this change).</span></span>

### <a name="powershell-as-a-default-shell-doesnt-work-with-script-command-3319"></a><span data-ttu-id="3cd90-257">PowerShell как оболочка по умолчанию не работает с командой скрипта [№ 3319](https://github.com/PowerShell/PowerShell/issues/3319)</span><span class="sxs-lookup"><span data-stu-id="3cd90-257">PowerShell as a default shell doesn't work with script command [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span></span>

<span data-ttu-id="3cd90-258">В Unix оболочки по умолчанию принимают `-i` для интерактивной оболочки. Многие инструменты ожидают такого поведения (например, `script` и при установке PowerShell в качестве оболочки по умолчанию) и вызывают оболочку с помощью параметра `-i`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-258">On Unix, it is a convention for shells to accept `-i` for an interactive shell and many tools expect this behavior (`script` for example, and when setting PowerShell as the default shell) and calls the shell with the `-i` switch.</span></span> <span data-ttu-id="3cd90-259">Это изменение является критическим, так как `-i` ранее можно было использовать как сокращение для сопоставления с параметром `-inputformat`, который теперь должен соответствовать `-in`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-259">This change is breaking in that `-i` previously could be used as short hand to match `-inputformat`, which now needs to be `-in`.</span></span>

### <a name="typo-fix-in-get-computerinfo-property-name-3167"></a><span data-ttu-id="3cd90-260">Исправлена опечатка в имени свойства Get-ComputerInfo [№ 3167](https://github.com/PowerShell/PowerShell/issues/3167)</span><span class="sxs-lookup"><span data-stu-id="3cd90-260">Typo fix in Get-ComputerInfo property name [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span></span>

<span data-ttu-id="3cd90-261">`BiosSerialNumber` был написан с ошибкой (как `BiosSeralNumber`). Теперь ошибка исправлена.</span><span class="sxs-lookup"><span data-stu-id="3cd90-261">`BiosSerialNumber` was misspelled as `BiosSeralNumber` and has been changed to the correct spelling.</span></span>

### <a name="add-get-stringhash-and-get-filehash-cmdlets-3024"></a><span data-ttu-id="3cd90-262">Добавлены командлеты `Get-StringHash` и `Get-FileHash`[№ 3024](https://github.com/PowerShell/PowerShell/issues/3024)</span><span class="sxs-lookup"><span data-stu-id="3cd90-262">Add `Get-StringHash` and `Get-FileHash` cmdlets [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span></span>

<span data-ttu-id="3cd90-263">Это изменение заключается в том, что некоторые хэш-алгоритмы не поддерживаются CoreFX, поэтому они больше недоступны:</span><span class="sxs-lookup"><span data-stu-id="3cd90-263">This change is that some hash algorithms are not supported by CoreFX, therefore they are no longer available:</span></span>

- `MACTripleDES`
- `RIPEMD160`

### <a name="add-validation-on-get--cmdlets-where-passing-null-returns-all-objects-instead-of-error-2672"></a><span data-ttu-id="3cd90-264">Добавлена проверка командлетов `Get-*`, в которых передача значения $null возвращала все объекты вместо ошибки [№ 2672](https://github.com/PowerShell/PowerShell/issues/2672)</span><span class="sxs-lookup"><span data-stu-id="3cd90-264">Add validation on `Get-*` cmdlets where passing $null returns all objects instead of error [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span></span>

<span data-ttu-id="3cd90-265">Передача `$null` в любой из следующих командлетов теперь вызывает ошибку:</span><span class="sxs-lookup"><span data-stu-id="3cd90-265">Passing `$null` to any of the following now throws an error:</span></span>

- `Get-Credential -UserName`
- `Get-Event -SourceIdentifier`
- `Get-EventSubscriber -SourceIdentifier`
- `Get-Help -Name`
- `Get-PSBreakpoint -Script`
- `Get-PSProvider -PSProvider`
- `Get-PSSessionConfiguration -Name`
- `Get-PSSnapin -Name`
- `Get-Runspace -Name`
- `Get-RunspaceDebug -RunspaceName`
- `Get-Service -Name`
- `Get-TraceSource -Name`
- `Get-Variable -Name`
- `Get-WmiObject -Class`
- `Get-WmiObject -Property`

### <a name="add-support-w3c-extended-log-file-format-in-import-csv-2482"></a><span data-ttu-id="3cd90-266">Добавлена поддержка расширенного формата файла журнала W3C в `Import-Csv` [№ 2482](https://github.com/PowerShell/PowerShell/issues/2482)</span><span class="sxs-lookup"><span data-stu-id="3cd90-266">Add support W3C Extended Log File Format in `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span></span>

<span data-ttu-id="3cd90-267">Ранее командлет `Import-Csv` не мог использоваться для непосредственного импорта файлов журнала в расширенный формат журнала W3C и требовалось дополнительное действие.</span><span class="sxs-lookup"><span data-stu-id="3cd90-267">Previously, the `Import-Csv` cmdlet cannot be used to directly import the log files in W3C extended log format and additional action would be required.</span></span> <span data-ttu-id="3cd90-268">Благодаря этому изменению теперь поддерживается расширенный формат журнала W3C.</span><span class="sxs-lookup"><span data-stu-id="3cd90-268">With this change, W3C extended log format is supported.</span></span>

### <a name="parameter-binding-problem-with-valuefromremainingarguments-in-ps-functions-2035"></a><span data-ttu-id="3cd90-269">Проблема привязки параметра с `ValueFromRemainingArguments` в функциях PS [№ 2035](https://github.com/PowerShell/PowerShell/issues/2035)</span><span class="sxs-lookup"><span data-stu-id="3cd90-269">Parameter binding problem with `ValueFromRemainingArguments` in PS functions [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span></span>

<span data-ttu-id="3cd90-270">`ValueFromRemainingArguments` теперь возвращает значения в виде массива, а не одного значения, которое само по себе являлось массивом.</span><span class="sxs-lookup"><span data-stu-id="3cd90-270">`ValueFromRemainingArguments` now returns the values as an array instead of a single value which itself is an array.</span></span>

### <a name="buildversion-is-removed-from-psversiontable-1415"></a><span data-ttu-id="3cd90-271">Свойство `BuildVersion` удалено из `$PSVersionTable` [№ 1415](https://github.com/PowerShell/PowerShell/issues/1415)</span><span class="sxs-lookup"><span data-stu-id="3cd90-271">`BuildVersion` is removed from `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span></span>

<span data-ttu-id="3cd90-272">Свойство `BuildVersion` удалено из `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-272">Remove the `BuildVersion` property from `$PSVersionTable`.</span></span> <span data-ttu-id="3cd90-273">Это свойство было привязано к версии сборки Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd90-273">This property was tied to the Windows build version.</span></span> <span data-ttu-id="3cd90-274">Вместо этого мы рекомендуем использовать `GitCommitId` для получения точной версии сборки PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="3cd90-274">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span>

### <a name="changes-to-web-cmdlets"></a><span data-ttu-id="3cd90-275">Изменения в веб-командлетах</span><span class="sxs-lookup"><span data-stu-id="3cd90-275">Changes to Web Cmdlets</span></span>

<span data-ttu-id="3cd90-276">Базовый API .NET веб-командлетов был изменен на `System.Net.Http.HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-276">The underlying .NET API of the Web Cmdlets has been changed to `System.Net.Http.HttpClient`.</span></span> <span data-ttu-id="3cd90-277">Это изменение предоставляет множество преимуществ.</span><span class="sxs-lookup"><span data-stu-id="3cd90-277">This change provides many benefits.</span></span> <span data-ttu-id="3cd90-278">Тем не менее это изменение вместе с недостатком взаимодействия с Internet Explorer привело к нескольким критическим изменениям в `Invoke-WebRequest` и `Invoke-RestMethod`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-278">However, this change along with a lack of interoperability with Internet Explorer have resulted in several breaking changes within `Invoke-WebRequest` and `Invoke-RestMethod`.</span></span>

- <span data-ttu-id="3cd90-279">`Invoke-WebRequest` теперь поддерживает только основной анализ HTML.</span><span class="sxs-lookup"><span data-stu-id="3cd90-279">`Invoke-WebRequest` now supports basic HTML Parsing only.</span></span> <span data-ttu-id="3cd90-280">`Invoke-WebRequest` всегда возвращает объект `BasicHtmlWebResponseObject`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-280">`Invoke-WebRequest` always returns a `BasicHtmlWebResponseObject` object.</span></span> <span data-ttu-id="3cd90-281">Свойства `ParsedHtml` и `Forms` были удалены.</span><span class="sxs-lookup"><span data-stu-id="3cd90-281">The `ParsedHtml` and `Forms` properties have been removed.</span></span>
- <span data-ttu-id="3cd90-282">Значения `BasicHtmlWebResponseObject.Headers` теперь имеют тип `String[]`, а не `String`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-282">`BasicHtmlWebResponseObject.Headers` values are now `String[]` instead of `String`.</span></span>
- <span data-ttu-id="3cd90-283">`BasicHtmlWebResponseObject.BaseResponse` теперь является объектом `System.Net.Http.HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-283">`BasicHtmlWebResponseObject.BaseResponse` is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="3cd90-284">Свойство `Response` в исключениях веб-командлетов теперь является объектом `System.Net.Http.HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-284">The `Response` property on Web Cmdlet exceptions is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="3cd90-285">Строгий анализ заголовка RFC теперь является поведением по умолчанию для параметров `-Headers` и `-UserAgent`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-285">Strict RFC header parsing is now default for the `-Headers` and `-UserAgent` parameter.</span></span> <span data-ttu-id="3cd90-286">Это можно обойти с помощью `-SkipHeaderValidation`.</span><span class="sxs-lookup"><span data-stu-id="3cd90-286">This can be bypassed with `-SkipHeaderValidation`.</span></span>
- <span data-ttu-id="3cd90-287">Схемы URI `file://` и `ftp://` больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3cd90-287">`file://` and `ftp://` URI schemes are no longer supported.</span></span>
- <span data-ttu-id="3cd90-288">Параметры `System.Net.ServicePointManager` больше не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="3cd90-288">`System.Net.ServicePointManager` settings are no longer honored.</span></span>
- <span data-ttu-id="3cd90-289">В настоящее время в macOS нет проверки подлинности на основе сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3cd90-289">There is currently no certificate based authentication available on macOS.</span></span>
- <span data-ttu-id="3cd90-290">Использование `-Credential` в URI `http://` завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3cd90-290">Use of `-Credential` over an `http://` URI will result in an error.</span></span> <span data-ttu-id="3cd90-291">Используйте URI `https://` или передайте параметр `-AllowUnencryptedAuthentication`, чтобы подавить ошибку.</span><span class="sxs-lookup"><span data-stu-id="3cd90-291">Use an `https://` URI or supply the `-AllowUnencryptedAuthentication` parameter to suppress the error.</span></span>
- <span data-ttu-id="3cd90-292">`-MaximumRedirection` теперь создает неустранимую ошибку, если попытки перенаправления превышают указанный предел, вместо возвращения результатов последнего перенаправления.</span><span class="sxs-lookup"><span data-stu-id="3cd90-292">`-MaximumRedirection` now produces a terminating error when redirection attempts exceed the provided limit instead of returning the results of the last redirection.</span></span>
- <span data-ttu-id="3cd90-293">В PowerShell 6.2 мы внесли изменения в кодировку UTF-8 по умолчанию для ответов JSON.</span><span class="sxs-lookup"><span data-stu-id="3cd90-293">In PowerShell 6.2, a change was made to default to UTF-8 encoding for JSON responses.</span></span> <span data-ttu-id="3cd90-294">Если для ответа JSON не указан набор символов, по умолчанию должна использоваться кодировка UTF-8 в соответствии с RFC 8259.</span><span class="sxs-lookup"><span data-stu-id="3cd90-294">When a charset is not supplied for a JSON response, the default encoding should be UTF-8 per RFC 8259.</span></span>
