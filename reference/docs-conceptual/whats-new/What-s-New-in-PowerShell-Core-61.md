---
title: Новые возможности PowerShell Core 6.1
description: Новые возможности и изменения в PowerShell Core 6.1
ms.date: 09/13/2018
ms.openlocfilehash: 079d5a472c743ce94f2e93143c1dcb4ff406951f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "78277757"
---
# <a name="whats-new-in-powershell-core-61"></a><span data-ttu-id="529bb-103">Новые возможности PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="529bb-103">What's New in PowerShell Core 6.1</span></span>

<span data-ttu-id="529bb-104">Ниже указаны некоторые основные новые функции и изменения, которые были введены в PowerShell Core 6.1.</span><span class="sxs-lookup"><span data-stu-id="529bb-104">Below is a selection of some of the major new features and changes that have been introduced in PowerShell Core 6.1.</span></span>

<span data-ttu-id="529bb-105">Кроме того, доступно **множество** добавлений, позволяющих повысить быстродействие и стабильность PowerShell (а также целый ряд исправлений ошибок).</span><span class="sxs-lookup"><span data-stu-id="529bb-105">There's also **tons** of "boring stuff" that make PowerShell faster and more stable (plus lots and lots of bug fixes)!</span></span> <span data-ttu-id="529bb-106">Полный список изменений см. в нашем [журнале изменений на сайте GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span><span class="sxs-lookup"><span data-stu-id="529bb-106">For a full list of changes, check out our [changelog on GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span></span>

<span data-ttu-id="529bb-107">Несмотря на то что далее мы называем лишь часть имен, мы выражаем благодарность [всем участникам сообщества](https://github.com/PowerShell/PowerShell/graphs/contributors), которые внесли свой вклад в этот выпуск.</span><span class="sxs-lookup"><span data-stu-id="529bb-107">And while we call out some names below, thank you to [all of the community contributors](https://github.com/PowerShell/PowerShell/graphs/contributors) that made this release possible.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="529bb-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="529bb-108">.NET Core 2.1</span></span>

<span data-ttu-id="529bb-109">После [выпуска в мае](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) среда PowerShell Core 6.1 перемещена на .NET Core 2.1, что привело к ряду улучшений в PowerShell, включая:</span><span class="sxs-lookup"><span data-stu-id="529bb-109">PowerShell Core 6.1 moved to .NET Core 2.1 after it was [released in May](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/), resulting in a number of improvements to PowerShell, including:</span></span>

- <span data-ttu-id="529bb-110">повышение производительности (см. [ниже](#performance-improvements));</span><span class="sxs-lookup"><span data-stu-id="529bb-110">performance improvements (see [below](#performance-improvements))</span></span>
- <span data-ttu-id="529bb-111">поддержку Alpine Linux (предварительная версия);</span><span class="sxs-lookup"><span data-stu-id="529bb-111">Alpine Linux support (preview)</span></span>
- <span data-ttu-id="529bb-112">[поддержку глобального средства .NET](/dotnet/core/tools/global-tools) — выходит в ближайшее время в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-112">[.NET global tool support](/dotnet/core/tools/global-tools) - coming soon to PowerShell</span></span>
- [`Span<T>`](/dotnet/api/system.span-1?view=netcore-2.1)

## <a name="windows-compatibility-pack-for-net-core"></a><span data-ttu-id="529bb-113">Пакет обеспечения совместимости Windows для .NET Core</span><span class="sxs-lookup"><span data-stu-id="529bb-113">Windows Compatibility Pack for .NET Core</span></span>

<span data-ttu-id="529bb-114">Команда разработчиков .NET добавила [пакет обеспечения совместимости Windows для .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/11/16/announcing-the-windows-compatibility-pack-for-net-core/) — набор сборок, которые добавляют несколько удаленных API-интерфейсов обратно в .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="529bb-114">On Windows, the .NET team shipped the [Windows Compatibility Pack for .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/11/16/announcing-the-windows-compatibility-pack-for-net-core/), a set of assemblies that add a number of removed APIs back to .NET Core on Windows.</span></span>

<span data-ttu-id="529bb-115">Мы добавили пакет обеспечения совместимости Windows в выпуск PowerShell Core 6.1, чтобы сделать доступными все модули или сценарии, использующие эти API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="529bb-115">We've added the Windows Compatibility Pack to PowerShell Core 6.1 release so that any modules or scripts that use these APIs can rely on them being available.</span></span>

<span data-ttu-id="529bb-116">Благодаря пакету обеспечения совместимости Windows в PowerShell Core можно использовать **более 1900 командлетов, входящих в состав обновления Windows от 10 октября 2018 г. и Windows Server 2019**.</span><span class="sxs-lookup"><span data-stu-id="529bb-116">The Windows Compatibility Pack enables PowerShell Core to use **more than 1900 cmdlets that ship with Windows 10 October 2018 Update and Windows Server 2019**.</span></span>

## <a name="support-for-application-whitelisting"></a><span data-ttu-id="529bb-117">Поддержка списков разрешенных приложений</span><span class="sxs-lookup"><span data-stu-id="529bb-117">Support for Application Whitelisting</span></span>

<span data-ttu-id="529bb-118">В PowerShell Core 6.1 реализована та же поддержка, что и в Windows PowerShell 5.1, которая позволяет добавлять приложения в список разрешенных в [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) и [Device Guard](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control).</span><span class="sxs-lookup"><span data-stu-id="529bb-118">PowerShell Core 6.1 has parity with Windows PowerShell 5.1 supporting [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) and [Device Guard](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control) application whitelisting.</span></span> <span data-ttu-id="529bb-119">Добавление приложений в список разрешенных обеспечивает более детализированное управление двоичными файлами, которые могут выполняться с помощью [ограниченного языкового режима](https://blogs.msdn.microsoft.com/powershell/2017/11/02/powershell-constrained-language-mode/) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-119">Application whitelisting allows granular control of what binaries are allowed to be executed used with PowerShell [Constrained Language mode](https://blogs.msdn.microsoft.com/powershell/2017/11/02/powershell-constrained-language-mode/).</span></span>

## <a name="performance-improvements"></a><span data-ttu-id="529bb-120">Повышение производительности</span><span class="sxs-lookup"><span data-stu-id="529bb-120">Performance improvements</span></span>

<span data-ttu-id="529bb-121">В PowerShell Core 6.0 внесены значительные усовершенствования производительности.</span><span class="sxs-lookup"><span data-stu-id="529bb-121">PowerShell Core 6.0 made some significant performance improvements.</span></span> <span data-ttu-id="529bb-122">PowerShell Core 6.1 и далее повышает скорость выполнения определенных операций.</span><span class="sxs-lookup"><span data-stu-id="529bb-122">PowerShell Core 6.1 continues to improve the speed of certain operations.</span></span>

<span data-ttu-id="529bb-123">Например, скорость выполнения `Group-Object` была увеличена до 66 %.</span><span class="sxs-lookup"><span data-stu-id="529bb-123">For example, `Group-Object` has been sped up by 66%:</span></span>

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Group-Object }
```

|              | <span data-ttu-id="529bb-124">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="529bb-124">Windows PowerShell 5.1</span></span> | <span data-ttu-id="529bb-125">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="529bb-125">PowerShell Core 6.0</span></span> | <span data-ttu-id="529bb-126">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="529bb-126">PowerShell Core 6.1</span></span> |
|--------------|------------------------|---------------------|---------------------|
| <span data-ttu-id="529bb-127">Время (с)</span><span class="sxs-lookup"><span data-stu-id="529bb-127">Time (sec)</span></span>   | <span data-ttu-id="529bb-128">25,178</span><span class="sxs-lookup"><span data-stu-id="529bb-128">25.178</span></span>                 | <span data-ttu-id="529bb-129">19,653</span><span class="sxs-lookup"><span data-stu-id="529bb-129">19.653</span></span>              | <span data-ttu-id="529bb-130">6,641</span><span class="sxs-lookup"><span data-stu-id="529bb-130">6.641</span></span>               |
| <span data-ttu-id="529bb-131">Ускорение (%)</span><span class="sxs-lookup"><span data-stu-id="529bb-131">Speed-up (%)</span></span> | <span data-ttu-id="529bb-132">Недоступно</span><span class="sxs-lookup"><span data-stu-id="529bb-132">N/A</span></span>                    | <span data-ttu-id="529bb-133">21,9 %</span><span class="sxs-lookup"><span data-stu-id="529bb-133">21.9%</span></span>               | <span data-ttu-id="529bb-134">66,2 %</span><span class="sxs-lookup"><span data-stu-id="529bb-134">66.2%</span></span>               |

<span data-ttu-id="529bb-135">Аналогично, более чем на 15 % улучшена производительность сценариев сортировки следующего вида.</span><span class="sxs-lookup"><span data-stu-id="529bb-135">Similarly, sorting scenarios like this one have improved by more than 15%:</span></span>

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Sort-Object }
```

|              | <span data-ttu-id="529bb-136">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="529bb-136">Windows PowerShell 5.1</span></span> | <span data-ttu-id="529bb-137">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="529bb-137">PowerShell Core 6.0</span></span> | <span data-ttu-id="529bb-138">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="529bb-138">PowerShell Core 6.1</span></span> |
|--------------|------------------------|---------------------|---------------------|
| <span data-ttu-id="529bb-139">Время (с)</span><span class="sxs-lookup"><span data-stu-id="529bb-139">Time (sec)</span></span>   | <span data-ttu-id="529bb-140">12,170</span><span class="sxs-lookup"><span data-stu-id="529bb-140">12.170</span></span>                 | <span data-ttu-id="529bb-141">8,493</span><span class="sxs-lookup"><span data-stu-id="529bb-141">8.493</span></span>               | <span data-ttu-id="529bb-142">7,08</span><span class="sxs-lookup"><span data-stu-id="529bb-142">7.08</span></span>                |
| <span data-ttu-id="529bb-143">Ускорение (%)</span><span class="sxs-lookup"><span data-stu-id="529bb-143">Speed-up (%)</span></span> | <span data-ttu-id="529bb-144">Недоступно</span><span class="sxs-lookup"><span data-stu-id="529bb-144">N/A</span></span>                    | <span data-ttu-id="529bb-145">30,2 %</span><span class="sxs-lookup"><span data-stu-id="529bb-145">30.2%</span></span>               | <span data-ttu-id="529bb-146">16,6 %</span><span class="sxs-lookup"><span data-stu-id="529bb-146">16.6%</span></span>               |

<span data-ttu-id="529bb-147">После регрессии из Windows PowerShell также было значительно ускорено выполнение `Import-Csv`.</span><span class="sxs-lookup"><span data-stu-id="529bb-147">`Import-Csv` has also been sped up significantly after a regression from Windows PowerShell.</span></span>
<span data-ttu-id="529bb-148">В следующем примере используется тестовый CSV-файл с 26 616 строками и шестью столбцами.</span><span class="sxs-lookup"><span data-stu-id="529bb-148">The following example uses a test CSV with 26,616 rows and six columns:</span></span>

```powershell
Measure-Command {$a = Import-Csv foo.csv}
```

|              | <span data-ttu-id="529bb-149">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="529bb-149">Windows PowerShell 5.1</span></span> | <span data-ttu-id="529bb-150">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="529bb-150">PowerShell Core 6.0</span></span> | <span data-ttu-id="529bb-151">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="529bb-151">PowerShell Core 6.1</span></span>    |
|--------------|------------------------|---------------------|------------------------|
| <span data-ttu-id="529bb-152">Время (с)</span><span class="sxs-lookup"><span data-stu-id="529bb-152">Time (sec)</span></span>   | <span data-ttu-id="529bb-153">0,441</span><span class="sxs-lookup"><span data-stu-id="529bb-153">0.441</span></span>                  | <span data-ttu-id="529bb-154">1,069</span><span class="sxs-lookup"><span data-stu-id="529bb-154">1.069</span></span>               | <span data-ttu-id="529bb-155">0,268</span><span class="sxs-lookup"><span data-stu-id="529bb-155">0.268</span></span>                  |
| <span data-ttu-id="529bb-156">Ускорение (%)</span><span class="sxs-lookup"><span data-stu-id="529bb-156">Speed-up (%)</span></span> | <span data-ttu-id="529bb-157">Недоступно</span><span class="sxs-lookup"><span data-stu-id="529bb-157">N/A</span></span>                    | <span data-ttu-id="529bb-158">–142,4 %</span><span class="sxs-lookup"><span data-stu-id="529bb-158">-142.4%</span></span>             | <span data-ttu-id="529bb-159">74,9 % (39,2 % в WPS)</span><span class="sxs-lookup"><span data-stu-id="529bb-159">74.9% (39.2% from WPS)</span></span> |

<span data-ttu-id="529bb-160">Наконец, преобразование из формата JSON в `PSObject` было ускорено более чем на 50 % по сравнению с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-160">Lastly, conversion from JSON into `PSObject` has been sped up by more than 50% since Windows PowerShell.</span></span>
<span data-ttu-id="529bb-161">В следующем примере используется тестовый JSON-файл размером около 2 МБ.</span><span class="sxs-lookup"><span data-stu-id="529bb-161">The following example uses a ~2MB test JSON file:</span></span>

```powershell
Measure-Command {Get-Content .\foo.json | ConvertFrom-Json}
```

|              | <span data-ttu-id="529bb-162">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="529bb-162">Windows PowerShell 5.1</span></span> | <span data-ttu-id="529bb-163">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="529bb-163">PowerShell Core 6.0</span></span> | <span data-ttu-id="529bb-164">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="529bb-164">PowerShell Core 6.1</span></span>    |
|--------------|------------------------|---------------------|------------------------|
| <span data-ttu-id="529bb-165">Время (с)</span><span class="sxs-lookup"><span data-stu-id="529bb-165">Time (sec)</span></span>   | <span data-ttu-id="529bb-166">0,259</span><span class="sxs-lookup"><span data-stu-id="529bb-166">0.259</span></span>                  | <span data-ttu-id="529bb-167">0,577</span><span class="sxs-lookup"><span data-stu-id="529bb-167">0.577</span></span>               | <span data-ttu-id="529bb-168">0.125</span><span class="sxs-lookup"><span data-stu-id="529bb-168">0.125</span></span>                  |
| <span data-ttu-id="529bb-169">Ускорение (%)</span><span class="sxs-lookup"><span data-stu-id="529bb-169">Speed-up (%)</span></span> | <span data-ttu-id="529bb-170">Недоступно</span><span class="sxs-lookup"><span data-stu-id="529bb-170">N/A</span></span>                    | <span data-ttu-id="529bb-171">–122,8 %</span><span class="sxs-lookup"><span data-stu-id="529bb-171">-122.8%</span></span>             | <span data-ttu-id="529bb-172">78,3 % (51,7 % в WPS)</span><span class="sxs-lookup"><span data-stu-id="529bb-172">78.3% (51.7% from WPS)</span></span> |

## <a name="check-system32-for-compatible-in-box-modules-on-windows"></a><span data-ttu-id="529bb-173">Проверка `system32` на наличие совместимых встроенных модулей в Windows</span><span class="sxs-lookup"><span data-stu-id="529bb-173">Check `system32` for compatible in-box modules on Windows</span></span>

<span data-ttu-id="529bb-174">В обновлении 1809 Windows 10 и Windows Server 2019 мы обновили несколько готовых модулей PowerShell, и теперь они могут помечаться как совместимые с PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="529bb-174">In the Windows 10 1809 update and Windows Server 2019, we updated a number of in-box PowerShell modules to mark them as compatible with PowerShell Core.</span></span>

<span data-ttu-id="529bb-175">При запуске PowerShell Core 6.1 будет автоматически включать `$windir\System32` как часть переменной среды `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="529bb-175">When PowerShell Core 6.1 starts up, it will automatically include `$windir\System32` as part of the `PSModulePath` environment variable.</span></span> <span data-ttu-id="529bb-176">Однако она предоставляет модули в `Get-Module` и `Import-Module`, только если `CompatiblePSEdition` помечен как совместимый с `Core`.</span><span class="sxs-lookup"><span data-stu-id="529bb-176">However, it only exposes modules to `Get-Module` and `Import-Module` if its `CompatiblePSEdition` is marked as compatible with `Core`.</span></span>


```powershell
Get-Module -ListAvailable
```

> [!NOTE]
> <span data-ttu-id="529bb-177">В зависимости от установленных ролей и компонентов будут доступны самые разные модули.</span><span class="sxs-lookup"><span data-stu-id="529bb-177">You may see different available modules depending on what roles and features are installed.</span></span>

```Output
...
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, Get-AppxPackage, Get-AppxPacka...
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, Suspend-BitLocker, Resume-Bit...
Manifest   1.0.0.0    DnsClient                           Core,Desk {Resolve-DnsName, Clear-DnsClientCache, Get-DnsC...
Manifest   1.0.0.0    HgsDiagnostics                      Core,Desk {New-HgsTraceTarget, Get-HgsTrace, Get-HgsTraceF...
Binary     2.0.0.0    Hyper-V                             Core,Desk {Add-VMAssignableDevice, Add-VMDvdDrive, Add-VMF...
Binary     1.1        Hyper-V                             Core,Desk {Add-VMDvdDrive, Add-VMFibreChannelHba, Add-VMHa...
Manifest   2.0.0.0    NetAdapter                          Core,Desk {Disable-NetAdapter, Disable-NetAdapterBinding, ...
Manifest   1.0.0.0    NetEventPacketCapture               Core,Desk {New-NetEventSession, Remove-NetEventSession, Ge...
Manifest   2.0.0.0    NetLbfo                             Core,Desk {Add-NetLbfoTeamMember, Add-NetLbfoTeamNic, Get-...
Manifest   1.0.0.0    NetNat                              Core,Desk {Get-NetNat, Get-NetNatExternalAddress, Get-NetN...
Manifest   2.0.0.0    NetQos                              Core,Desk {Get-NetQosPolicy, Set-NetQosPolicy, Remove-NetQ...
Manifest   2.0.0.0    NetSecurity                         Core,Desk {Get-DAPolicyChange, New-NetIPsecAuthProposal, N...
Manifest   1.0.0.0    NetSwitchTeam                       Core,Desk {New-NetSwitchTeam, Remove-NetSwitchTeam, Get-Ne...
Manifest   1.0.0.0    NetWNV                              Core,Desk {Get-NetVirtualizationProviderAddress, Get-NetVi...
Manifest   2.0.0.0    TrustedPlatformModule               Core,Desk {Get-Tpm, Initialize-Tpm, Clear-Tpm, Unblock-Tpm...
...
```

<span data-ttu-id="529bb-178">С помощью параметра `-SkipEditionCheck` это поведение можно переопределить для отображения всех модулей.</span><span class="sxs-lookup"><span data-stu-id="529bb-178">You can override this behavior to show all modules using the `-SkipEditionCheck` switch parameter.</span></span>
<span data-ttu-id="529bb-179">Мы также добавили свойство `PSEdition` в выходные данные таблицы.</span><span class="sxs-lookup"><span data-stu-id="529bb-179">We've also added a `PSEdition` property to the table output.</span></span>

```powershell
Get-Module Net* -ListAvailable -SkipEditionCheck
```

```Output
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                        PSEdition ExportedCommands
---------- -------    ----                        --------- ----------------
Manifest   2.0.0.0    NetAdapter                  Core,Desk {Disable-NetAdapter, Disable-NetAdapterBinding, ...
Manifest   1.0.0.0    NetConnection               Core,Desk {Get-NetConnectionProfile, Set-NetConnectionProf...
Manifest   1.0.0.0    NetDiagnostics              Desk      Get-NetView
Manifest   1.0.0.0    NetEventPacketCapture       Core,Desk {New-NetEventSession, Remove-NetEventSession, Ge...
Manifest   2.0.0.0    NetLbfo                     Core,Desk {Add-NetLbfoTeamMember, Add-NetLbfoTeamNic, Get-...
Manifest   1.0.0.0    NetNat                      Core,Desk {Get-NetNat, Get-NetNatExternalAddress, Get-NetN...
Manifest   2.0.0.0    NetQos                      Core,Desk {Get-NetQosPolicy, Set-NetQosPolicy, Remove-NetQ...
Manifest   2.0.0.0    NetSecurity                 Core,Desk {Get-DAPolicyChange, New-NetIPsecAuthProposal, N...
Manifest   1.0.0.0    NetSwitchTeam               Core,Desk {New-NetSwitchTeam, Remove-NetSwitchTeam, Get-Ne...
Manifest   1.0.0.0    NetTCPIP                    Core,Desk {Get-NetIPAddress, Get-NetIPInterface, Get-NetIP...
Manifest   1.0.0.0    NetWNV                      Core,Desk {Get-NetVirtualizationProviderAddress, Get-NetVi...
Manifest   1.0.0.0    NetworkConnectivityStatus   Core,Desk {Get-DAConnectionStatus, Get-NCSIPolicyConfigura...
Manifest   1.0.0.0    NetworkSwitchManager        Core,Desk {Disable-NetworkSwitchEthernetPort, Enable-Netwo...
Manifest   1.0.0.0    NetworkTransition           Core,Desk {Add-NetIPHttpsCertBinding, Disable-NetDnsTransi...
```

<span data-ttu-id="529bb-180">Дополнительные сведения об этом поведении см. в [PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md).</span><span class="sxs-lookup"><span data-stu-id="529bb-180">For more information about this behavior, check out [PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md).</span></span>

## <a name="markdown-cmdlets-and-rendering"></a><span data-ttu-id="529bb-181">Командлеты и отрисовка Markdown</span><span class="sxs-lookup"><span data-stu-id="529bb-181">Markdown cmdlets and rendering</span></span>

<span data-ttu-id="529bb-182">Markdown — это стандарт для создания документов с читаемым открытым текстом с базовым форматированием, которое может отображаться в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="529bb-182">Markdown is a standard for creating readable plaintext documents with basic formatting that can be rendered into HTML.</span></span>

<span data-ttu-id="529bb-183">Мы добавили в версию 6.1 несколько командлетов, которые позволяют преобразовывать и отображать документы Markdown.</span><span class="sxs-lookup"><span data-stu-id="529bb-183">We've added some cmdlets in 6.1 that allow you to convert and render Markdown documents in the console, including:</span></span>

- `ConvertFrom-Markdown`
- `Get-MarkdownOption`
- `Set-MarkdownOption`
- `Show-Markdown`

<span data-ttu-id="529bb-184">Например, `Show-Markdown` отрисовывает файл Markdown в консоли.</span><span class="sxs-lookup"><span data-stu-id="529bb-184">For example, `Show-Markdown` renders a Markdown file in the console:</span></span>

![Пример Show-Markdown](media/What-s-New-in-PowerShell-Core-61/markdown_example.png)

<span data-ttu-id="529bb-186">Дополнительные сведения об использовании этих командлетов см. в [этом документе RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md).</span><span class="sxs-lookup"><span data-stu-id="529bb-186">For more information about how these cmdlets work, check out [this RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md).</span></span>

## <a name="experimental-feature-flags"></a><span data-ttu-id="529bb-187">Флаги экспериментальных функций</span><span class="sxs-lookup"><span data-stu-id="529bb-187">Experimental feature flags</span></span>

<span data-ttu-id="529bb-188">Мы включили поддержку [Экспериментальные возможности][].</span><span class="sxs-lookup"><span data-stu-id="529bb-188">We enabled support for [Experimental Features][].</span></span> <span data-ttu-id="529bb-189">Это позволяет разработчикам PowerShell предлагать новые функций и получать отзывы до завершения разработки новой версии.</span><span class="sxs-lookup"><span data-stu-id="529bb-189">This allows PowerShell developers to deliver new features and get feedback before the design is complete.</span></span> <span data-ttu-id="529bb-190">Благодаря этому мы можем не вносить критические изменения пока версия разрабатывается.</span><span class="sxs-lookup"><span data-stu-id="529bb-190">This way we avoid making breaking changes as the design evolves.</span></span>

<span data-ttu-id="529bb-191">Используйте командлет `Get-ExperimentalFeature`, чтобы получить список доступных экспериментальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="529bb-191">Use `Get-ExperimentalFeature` to get a list of available experimental features.</span></span> <span data-ttu-id="529bb-192">Их можно включить и отключить с помощью `Enable-ExperimentalFeature` и `Disable-ExperimentalFeature` соответственно.</span><span class="sxs-lookup"><span data-stu-id="529bb-192">You can enable or disable these features with `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature`.</span></span>

<span data-ttu-id="529bb-193">Дополнительные сведения об этой функции см. в [PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md).</span><span class="sxs-lookup"><span data-stu-id="529bb-193">You can learn more about this feature in [PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md).</span></span>

## <a name="web-cmdlet-improvements"></a><span data-ttu-id="529bb-194">Усовершенствования веб-командлетов</span><span class="sxs-lookup"><span data-stu-id="529bb-194">Web cmdlet improvements</span></span>

<span data-ttu-id="529bb-195">Выражаем благодарность [@markekraus](https://github.com/markekraus) за улучшения, внесенные в веб-командлеты: [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span><span class="sxs-lookup"><span data-stu-id="529bb-195">Thanks to [@markekraus](https://github.com/markekraus), a whole slew of improvements have been made to our web cmdlets: [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span></span>
<span data-ttu-id="529bb-196">и [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod).</span><span class="sxs-lookup"><span data-stu-id="529bb-196">and [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod).</span></span>

- <span data-ttu-id="529bb-197">[PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) — по умолчанию задана кодировка UTF-8 для ответов `application-json`</span><span class="sxs-lookup"><span data-stu-id="529bb-197">[PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) - default encoding set to UTF-8 for `application-json` responses</span></span>
- <span data-ttu-id="529bb-198">[PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - — параметр `-SkipHeaderValidation`, позволяющий использовать заголовки `Content-Type`, которые не соответствуют стандартам</span><span class="sxs-lookup"><span data-stu-id="529bb-198">[PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - `-SkipHeaderValidation` parameter to allow `Content-Type` headers that aren't standards-compliant</span></span>
- <span data-ttu-id="529bb-199">[PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - — параметр `Form` для упрощенной поддержки `multipart/form-data`</span><span class="sxs-lookup"><span data-stu-id="529bb-199">[PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - `Form` parameter to support simplified `multipart/form-data` support</span></span>
- <span data-ttu-id="529bb-200">[PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) — соответствующая, не учитывающая регистр обработка ключей отношения</span><span class="sxs-lookup"><span data-stu-id="529bb-200">[PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) - Compliant, case-insensitive handling of relation keys</span></span>
- <span data-ttu-id="529bb-201">[PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) — добавление параметра `-Resume` для веб-командлетов</span><span class="sxs-lookup"><span data-stu-id="529bb-201">[PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) - Add `-Resume` parameter for web cmdlets</span></span>

## <a name="remoting-improvements"></a><span data-ttu-id="529bb-202">Усовершенствования удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="529bb-202">Remoting improvements</span></span>

### <a name="powershell-direct-for-containers-tries-to-use-powershell-core-first"></a><span data-ttu-id="529bb-203">PowerShell Direct для контейнеров сначала пытается использовать PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="529bb-203">PowerShell Direct for Containers tries to use PowerShell Core first</span></span>

<span data-ttu-id="529bb-204">[PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) входит в состав PowerShell и Hyper-V и позволяет подключаться к виртуальной машине Hyper-V или контейнеру без сетевого соединения или других служб удаленного управления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-204">[PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) is a feature of PowerShell and Hyper-V that allows you to connect to a Hyper-V VM or Container without network connectivity or other remote management services.</span></span>

<span data-ttu-id="529bb-205">В прошлом для подключения PowerShell Direct использовался готовый экземпляр Windows PowerShell в контейнере.</span><span class="sxs-lookup"><span data-stu-id="529bb-205">In the past, PowerShell Direct connected using the inbox Windows PowerShell instance on the Container.</span></span> <span data-ttu-id="529bb-206">Теперь PowerShell Direct сначала пытается подключиться с помощью любого доступного `pwsh.exe` в переменной среды`PATH`.</span><span class="sxs-lookup"><span data-stu-id="529bb-206">Now, PowerShell Direct first attempts to connect using any available `pwsh.exe` on the `PATH` environment variable.</span></span> <span data-ttu-id="529bb-207">Если `pwsh.exe` недоступен, PowerShell Direct переключается на использование `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="529bb-207">If `pwsh.exe` isn't available, PowerShell Direct falls back to use `powershell.exe`.</span></span>

### <a name="enable-psremoting-now-creates-separate-remoting-endpoints-for-preview-versions"></a><span data-ttu-id="529bb-208">`Enable-PSRemoting` теперь создает отдельные конечные точки удаленного взаимодействия для предварительных версий</span><span class="sxs-lookup"><span data-stu-id="529bb-208">`Enable-PSRemoting` now creates separate remoting endpoints for preview versions</span></span>

<span data-ttu-id="529bb-209">`Enable-PSRemoting` теперь создает две конфигурации сеанса удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="529bb-209">`Enable-PSRemoting` now creates two remoting session configurations:</span></span>

- <span data-ttu-id="529bb-210">Одна для основного номера версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-210">One for the major version of PowerShell.</span></span> <span data-ttu-id="529bb-211">Например, `PowerShell.6`.</span><span class="sxs-lookup"><span data-stu-id="529bb-211">For example, `PowerShell.6`.</span></span> <span data-ttu-id="529bb-212">Эта конечная точка может быть основной в обновлениях дополнительного номера версии как конфигурация сеанса PowerShell 6 на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="529bb-212">This endpoint that can be relied upon across minor version updates as the "system-wide" PowerShell 6 session configuration</span></span>
- <span data-ttu-id="529bb-213">Одна конфигурация сеанса для конкретной версии, например: `PowerShell.6.1.0`</span><span class="sxs-lookup"><span data-stu-id="529bb-213">One version-specific session configuration, for example: `PowerShell.6.1.0`</span></span>

<span data-ttu-id="529bb-214">Это полезно, если вы хотите, чтобы на одном компьютере было установлено и доступно несколько версий PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="529bb-214">This behavior is useful if you want to have multiple PowerShell 6 versions installed and accessible on the same machine.</span></span>

<span data-ttu-id="529bb-215">Кроме того, теперь в предварительных версиях PowerShell доступны собственные конфигурации сеанса удаленного взаимодействия после выполнения командлета `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="529bb-215">Additionally, preview versions of PowerShell now get their own remoting session configurations after running the `Enable-PSRemoting` cmdlet:</span></span>

```powershell
C:\WINDOWS\system32> Enable-PSRemoting
```

<span data-ttu-id="529bb-216">Если вы еще не настроили WinRM, выходные данные могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="529bb-216">Your output may be different if you haven't set up WinRM before.</span></span>

```Output
WinRM is already set up to receive requests on this computer.
WinRM is already set up for remote management on this computer.
```

<span data-ttu-id="529bb-217">Затем вы увидите отдельные конфигурации сеанса PowerShell для предварительных и стабильных сборок PowerShell 6, а также для каждой конкретной версии.</span><span class="sxs-lookup"><span data-stu-id="529bb-217">Then you can see separate PowerShell session configurations for the preview and stable builds of PowerShell 6, and for each specific version.</span></span>

```powershell
Get-PSSessionConfiguration
```

```Output
Name          : PowerShell.6.2-preview.1
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6-preview
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : powershell.6
PSVersion     : 6.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : powershell.6.1.0
PSVersion     : 6.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

### <a name="userhostport-syntax-supported-for-ssh"></a><span data-ttu-id="529bb-218">Синтаксис `user@host:port`, поддерживаемый для SSH</span><span class="sxs-lookup"><span data-stu-id="529bb-218">`user@host:port` syntax supported for SSH</span></span>

<span data-ttu-id="529bb-219">SSH-клиенты обычно поддерживают строки подключения в формате `user@host:port`.</span><span class="sxs-lookup"><span data-stu-id="529bb-219">SSH clients typically support a connection string in the format `user@host:port`.</span></span> <span data-ttu-id="529bb-220">С появлением SSH как протокола для удаленного взаимодействия PowerShell мы добавили поддержку этого формата строки подключения.</span><span class="sxs-lookup"><span data-stu-id="529bb-220">With the addition of SSH as a protocol for PowerShell Remoting, we've added support for this format of connection string:</span></span>

`Enter-PSSession -HostName fooUser@ssh.contoso.com:2222`

## <a name="msi-option-to-add-explorer-shell-context-menu-on-windows"></a><span data-ttu-id="529bb-221">Параметр MSI для добавления контекстного меню оболочки Проводника в Windows</span><span class="sxs-lookup"><span data-stu-id="529bb-221">MSI option to add explorer shell context menu on Windows</span></span>

<span data-ttu-id="529bb-222">Выражаем благодарность [@bergmeister](https://github.com/bergmeister), так как теперь можно включать контекстное меню в Windows.</span><span class="sxs-lookup"><span data-stu-id="529bb-222">Thanks to [@bergmeister](https://github.com/bergmeister), now you can enable a context menu on Windows.</span></span> <span data-ttu-id="529bb-223">Вы можете открыть системную установку PowerShell 6.1 из любой папки в Проводнике Windows.</span><span class="sxs-lookup"><span data-stu-id="529bb-223">Now you can open your system-wide installation of PowerShell 6.1 from any folder in the Windows Explorer:</span></span>

![Контекстное меню оболочки для PowerShell 6](media/What-s-New-in-PowerShell-Core-61/shell_context_menu.png)

## <a name="goodies"></a><span data-ttu-id="529bb-225">Полезные возможности</span><span class="sxs-lookup"><span data-stu-id="529bb-225">Goodies</span></span>

### <a name="run-as-administrator-in-the-windows-shortcut-jump-list"></a><span data-ttu-id="529bb-226">"Запуск от имени администратора" в списке переходов в Windows</span><span class="sxs-lookup"><span data-stu-id="529bb-226">"Run as Administrator" in the Windows shortcut jump list</span></span>

<span data-ttu-id="529bb-227">Выражаем благодарность [@bergmeister](https://github.com/bergmeister), так как теперь список переходов ярлыка PowerShell Core содержит возможность "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="529bb-227">Thanks to [@bergmeister](https://github.com/bergmeister), the PowerShell Core shortcut's jump list now includes "Run as Administrator":</span></span>

!["Запуск от имени администратора" в списке переходов PowerShell 6](media/What-s-New-in-PowerShell-Core-61/jumplist.png)

### <a name="cd---returns-to-previous-directory"></a><span data-ttu-id="529bb-229">`cd -` возвращается в предыдущий каталог</span><span class="sxs-lookup"><span data-stu-id="529bb-229">`cd -` returns to previous directory</span></span>

```powershell
C:\Windows\System32> cd C:\
C:\> cd -
C:\Windows\System32>
```

<span data-ttu-id="529bb-230">Или в Linux</span><span class="sxs-lookup"><span data-stu-id="529bb-230">Or on Linux:</span></span>

```ShellSession
PS /etc> cd /usr/bin
PS /usr/bin> cd -
PS /etc>
```

<span data-ttu-id="529bb-231">Кроме того, `cd` и `cd --` изменяются на `$HOME`.</span><span class="sxs-lookup"><span data-stu-id="529bb-231">Also, `cd` and `cd --` change to `$HOME`.</span></span>

### `Test-Connection`

<span data-ttu-id="529bb-232">Выражаем благодарность [@iSazonov](https://github.com/iSazonov) за перенос командлета [`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="529bb-232">Thanks to [@iSazonov](https://github.com/iSazonov), the [`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) cmdlet has been ported to PowerShell Core.</span></span>

### <a name="update-help-as-non-admin"></a><span data-ttu-id="529bb-233">Запуск `Update-Help` без прав администратора</span><span class="sxs-lookup"><span data-stu-id="529bb-233">`Update-Help` as non-admin</span></span>

<span data-ttu-id="529bb-234">По многочисленным просьбам `Update-Help` больше не требуется запускать от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="529bb-234">By popular demand, `Update-Help` no longer needs to be run as an administrator.</span></span> <span data-ttu-id="529bb-235">Теперь `Update-Help` по умолчанию сохраняет справку в папку пользователя.</span><span class="sxs-lookup"><span data-stu-id="529bb-235">`Update-Help` now defaults to saving help to a user-scoped folder.</span></span>

### <a name="new-methodsproperties-on-pscustomobject"></a><span data-ttu-id="529bb-236">Новые методы и свойства в `PSCustomObject`</span><span class="sxs-lookup"><span data-stu-id="529bb-236">New methods/properties on `PSCustomObject`</span></span>

<span data-ttu-id="529bb-237">Благодаря [@iSazonov](https://github.com/iSazonov) мы добавили новые методы и свойства в `PSCustomObject`.</span><span class="sxs-lookup"><span data-stu-id="529bb-237">Thanks to [@iSazonov](https://github.com/iSazonov), we've added new methods and properties to `PSCustomObject`.</span></span> <span data-ttu-id="529bb-238">`PSCustomObject` теперь включает свойство `Count`/`Length`, как и другие объекты.</span><span class="sxs-lookup"><span data-stu-id="529bb-238">`PSCustomObject` now includes a `Count`/`Length` property like other objects.</span></span>

```powershell
$PSCustomObject = [pscustomobject]@{foo = 1}

$PSCustomObject.Length
```

```Output
1
```

```powershell
$PSCustomObject.Count
```

```Output
1
```

<span data-ttu-id="529bb-239">Здесь также используются методы `ForEach` и `Where` методы, которые позволяют работать с элементами `PSCustomObject` и фильтровать их.</span><span class="sxs-lookup"><span data-stu-id="529bb-239">This work also includes `ForEach` and `Where` methods that allow you to operate and filter on `PSCustomObject` items:</span></span>

```powershell
$PSCustomObject.ForEach({$_.foo + 1})
```

```Output
2
```

```powershell
$PSCustomObject.Where({$_.foo -gt 0})
```

```Output
foo
---
  1
```

### `Where-Object -Not`

<span data-ttu-id="529bb-240">Благодаря @SimonWahlin мы добавили параметр `-Not` в `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="529bb-240">Thanks to @SimonWahlin, we've added the `-Not` parameter to `Where-Object`.</span></span> <span data-ttu-id="529bb-241">Теперь вы можете отфильтровать объект в конвейере для получения отсутствия свойства или нулевого и пустого значения свойства.</span><span class="sxs-lookup"><span data-stu-id="529bb-241">Now you can filter an object at the pipeline for the non-existence of a property, or a null/empty property value.</span></span>

<span data-ttu-id="529bb-242">Например, эта команда возвращает все службы, у которых нет зависимых служб.</span><span class="sxs-lookup"><span data-stu-id="529bb-242">For example, this command returns all services that don't have any dependent services defined:</span></span>

```powershell
Get-Service | Where-Object -Not DependentServices
```

### <a name="new-modulemanifest-creates-a-bom-less-utf-8-document"></a><span data-ttu-id="529bb-243">`New-ModuleManifest` создает документ в UTF-8 без BOM</span><span class="sxs-lookup"><span data-stu-id="529bb-243">`New-ModuleManifest` creates a BOM-less UTF-8 document</span></span>

<span data-ttu-id="529bb-244">Учитывая наш переход на UTF-8 без BOM в PowerShell 6.0, мы обновили командлет `New-ModuleManifest`, чтобы вместо документа в UTF-16 создавать документ в UTF-8 без BOM.</span><span class="sxs-lookup"><span data-stu-id="529bb-244">Given our move to BOM-less UTF-8 in PowerShell 6.0, we've updated the `New-ModuleManifest` cmdlet to create a BOM-less UTF-8 document instead of a UTF-16 one.</span></span>

### <a name="conversions-from-psmethod-to-delegate"></a><span data-ttu-id="529bb-245">Преобразования из PSMethod в делегат</span><span class="sxs-lookup"><span data-stu-id="529bb-245">Conversions from PSMethod to Delegate</span></span>

<span data-ttu-id="529bb-246">Выражаем благодарность [@powercode](https://github.com/powercode), так как теперь поддерживается преобразование `PSMethod` в делегат.</span><span class="sxs-lookup"><span data-stu-id="529bb-246">Thanks to [@powercode](https://github.com/powercode), we now support the conversion of a `PSMethod` into a delegate.</span></span> <span data-ttu-id="529bb-247">Это позволяет выполнять такие действия, как передача `PSMethod` `[M]::DoubleStrLen` в виде значения делегата в `[M]::AggregateString`.</span><span class="sxs-lookup"><span data-stu-id="529bb-247">This allows you to do things like passing `PSMethod` `[M]::DoubleStrLen` as a delegate value into `[M]::AggregateString`:</span></span>

```powershell
class M {
    static [int] DoubleStrLen([string] $value) { return 2 * $value.Length }

    static [long] AggregateString([string[]] $values, [func[string, int]] $selector) {
        [long] $res = 0
        foreach($s in $values){
            $res += $selector.Invoke($s)
        }
        return $res
    }
}

[M]::AggregateString((gci).Name, [M]::DoubleStrLen)
```

<span data-ttu-id="529bb-248">Дополнительные сведения об этом изменении см. в [PR #5287](https://github.com/PowerShell/PowerShell/pull/5287).</span><span class="sxs-lookup"><span data-stu-id="529bb-248">For more info on this change, check out [PR #5287](https://github.com/PowerShell/PowerShell/pull/5287).</span></span>

### <a name="standard-deviation-in-measure-object"></a><span data-ttu-id="529bb-249">Стандартное отклонение в `Measure-Object`</span><span class="sxs-lookup"><span data-stu-id="529bb-249">Standard deviation in `Measure-Object`</span></span>

<span data-ttu-id="529bb-250">Благодаря [@CloudyDino](https://github.com/CloudyDino) мы добавили свойство `StandardDeviation` в `Measure-Object`.</span><span class="sxs-lookup"><span data-stu-id="529bb-250">Thanks to [@CloudyDino](https://github.com/CloudyDino), we've added a `StandardDeviation` property to `Measure-Object`:</span></span>

```powershell
Get-Process | Measure-Object -Property CPU -AllStats
```

```Output
Count             : 308
Average           : 31.3720576298701
Sum               : 9662.59375
Maximum           : 4416.046875
Minimum           :
StandardDeviation : 264.389544720926
Property          : CPU
```

### `GetPfxCertificate -Password`

<span data-ttu-id="529bb-251">Выражаем благодарность [@maybe-hello-world](https://github.com/maybe-hello-world), так как `Get-PfxCertificate` теперь имеет `Password` параметр, который принимает `SecureString`.</span><span class="sxs-lookup"><span data-stu-id="529bb-251">Thanks to [@maybe-hello-world](https://github.com/maybe-hello-world), `Get-PfxCertificate` now has the `Password` parameter, which takes a `SecureString`.</span></span> <span data-ttu-id="529bb-252">Это позволяет вам использовать его не интерактивно.</span><span class="sxs-lookup"><span data-stu-id="529bb-252">This allows you to use it non-interactively:</span></span>

```powershell
$certFile = '\\server\share\pwd-protected.pfx'
$certPass = Read-Host -AsSecureString -Prompt 'Enter the password for certificate: '

$certThumbPrint = (Get-PfxCertificate -FilePath $certFile -Password $certPass ).ThumbPrint
```

### <a name="removal-of-the-more-function"></a><span data-ttu-id="529bb-253">Удаление функции `more`</span><span class="sxs-lookup"><span data-stu-id="529bb-253">Removal of the `more` function</span></span>

<span data-ttu-id="529bb-254">Раньше в состав PowerShell входила функция Windows `more`, которая упаковывала `more.com`.</span><span class="sxs-lookup"><span data-stu-id="529bb-254">In the past, PowerShell shipped a function on Windows called `more` that wrapped `more.com`.</span></span> <span data-ttu-id="529bb-255">Сейчас эта функция удалена.</span><span class="sxs-lookup"><span data-stu-id="529bb-255">That function has now been removed.</span></span>

<span data-ttu-id="529bb-256">Кроме того, функция `help` теперь использует команду `more.com` в Windows или системную команду просмотра по умолчанию, определяемую `$env:PAGER`, на других платформах.</span><span class="sxs-lookup"><span data-stu-id="529bb-256">Also, the `help` function changed to use `more.com` on Windows, or the system's default pager specified by `$env:PAGER` on non-Windows platforms.</span></span>

### <a name="cd-drivename-now-returns-users-to-the-current-working-directory-in-that-drive"></a><span data-ttu-id="529bb-257">Теперь `cd DriveName:` возвращает пользователей в текущий рабочий каталог на этом диске</span><span class="sxs-lookup"><span data-stu-id="529bb-257">`cd DriveName:` now returns users to the current working directory in that drive</span></span>

<span data-ttu-id="529bb-258">Раньше при использовании `Set-Location` или `cd` для возврата на PSDrive пользователи отправлялись в расположение по умолчанию для этого диска.</span><span class="sxs-lookup"><span data-stu-id="529bb-258">Previously, using `Set-Location` or `cd` to return to a PSDrive sent users to the default location for that drive.</span></span>

<span data-ttu-id="529bb-259">Выражаем благодарность [@mcbobke](https://github.com/mcbobke), так как теперь пользователи отправляются в последний известный текущий рабочий каталог для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="529bb-259">Thanks to [@mcbobke](https://github.com/mcbobke), users are now sent to the last known current working directory for that session.</span></span>

### <a name="windows-powershell-type-accelerators"></a><span data-ttu-id="529bb-260">Ускорители типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="529bb-260">Windows PowerShell type accelerators</span></span>

<span data-ttu-id="529bb-261">Мы включили в Windows PowerShell следующие ускорители типов для упрощения работы с их соответствующими типами.</span><span class="sxs-lookup"><span data-stu-id="529bb-261">In Windows PowerShell, we included the following type accelerators to make it easier to work with their respective types:</span></span>

- <span data-ttu-id="529bb-262">`[adsi]`: `System.DirectoryServices.DirectoryEntry`</span><span class="sxs-lookup"><span data-stu-id="529bb-262">`[adsi]`: `System.DirectoryServices.DirectoryEntry`</span></span>
- <span data-ttu-id="529bb-263">`[adsisearcher]`: `System.DirectoryServices.DirectorySearcher`</span><span class="sxs-lookup"><span data-stu-id="529bb-263">`[adsisearcher]`: `System.DirectoryServices.DirectorySearcher`</span></span>
- <span data-ttu-id="529bb-264">`[wmi]`: `System.Management.ManagementObject`</span><span class="sxs-lookup"><span data-stu-id="529bb-264">`[wmi]`: `System.Management.ManagementObject`</span></span>
- <span data-ttu-id="529bb-265">`[wmiclass]`: `System.Management.ManagementClass`</span><span class="sxs-lookup"><span data-stu-id="529bb-265">`[wmiclass]`: `System.Management.ManagementClass`</span></span>
- <span data-ttu-id="529bb-266">`[wmisearcher]`: `System.Management.ManagementObjectSearcher`</span><span class="sxs-lookup"><span data-stu-id="529bb-266">`[wmisearcher]`: `System.Management.ManagementObjectSearcher`</span></span>

<span data-ttu-id="529bb-267">Эти ускорители не были включены в PowerShell 6, но были добавлены в PowerShell 6.1 в Windows.</span><span class="sxs-lookup"><span data-stu-id="529bb-267">These type accelerators were not included in PowerShell 6, but have been added to PowerShell 6.1 running on Windows.</span></span>

<span data-ttu-id="529bb-268">Эти типы полезны при создании объектов AD и WMI.</span><span class="sxs-lookup"><span data-stu-id="529bb-268">These types are useful in easily constructing AD and WMI objects.</span></span>

<span data-ttu-id="529bb-269">Например, можно выполнить запрос с помощью LDAP.</span><span class="sxs-lookup"><span data-stu-id="529bb-269">For example, you can query using LDAP:</span></span>

```powershell
[adsi]'LDAP://CN=FooUse,OU=People,DC=contoso,DC=com'
```

<span data-ttu-id="529bb-270">В следующем примере создается объект CIM Win32_OperatingSystem.</span><span class="sxs-lookup"><span data-stu-id="529bb-270">Following example creates a Win32_OperatingSystem CIM object:</span></span>

```powershell
[wmi]"Win32_OperatingSystem=@"
```

```Output
SystemDirectory : C:\WINDOWS\system32
Organization    : Contoso IT
BuildNumber     : 18234
RegisteredUser  : Contoso Corp.
SerialNumber    : 12345-67890-ABCDE-F0123
Version         : 10.0.18234
```

<span data-ttu-id="529bb-271">Этот пример возвращает объект ManagementClass для класса Win32_OperatingSystem.</span><span class="sxs-lookup"><span data-stu-id="529bb-271">This example returns a ManagementClass object for Win32_OperatingSystem class.</span></span>

```powershell
[wmiclass]"Win32_OperatingSystem"
```

```Output
   NameSpace: ROOT\cimv2

Name                                Methods              Properties
----                                -------              ----------
Win32_OperatingSystem               {Reboot, Shutdown... {BootDevice, BuildNumber, BuildType, Caption...}
```

### <a name="-lp-alias-for-all--literalpath-parameters"></a><span data-ttu-id="529bb-272">Псевдоним `-lp` для всех параметров `-LiteralPath`</span><span class="sxs-lookup"><span data-stu-id="529bb-272">`-lp` alias for all `-LiteralPath` parameters</span></span>

<span data-ttu-id="529bb-273">Выражаем благодарность [@kvprasoon](https://github.com/kvprasoon), так как теперь у нас есть псевдоним параметра `-lp` для всех встроенных командлетов PowerShell, у которых есть параметр `-LiteralPath`.</span><span class="sxs-lookup"><span data-stu-id="529bb-273">Thanks to [@kvprasoon](https://github.com/kvprasoon), we now have a parameter alias `-lp` for all the built-in PowerShell cmdlets that have a `-LiteralPath` parameter.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="529bb-274">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="529bb-274">Breaking Changes</span></span>

### <a name="msi-based-installation-paths-on-windows"></a><span data-ttu-id="529bb-275">Пути установки на основе MSI в Windows</span><span class="sxs-lookup"><span data-stu-id="529bb-275">MSI-based installation paths on Windows</span></span>

<span data-ttu-id="529bb-276">Теперь в Windows пакет MSI устанавливается по следующему пути:</span><span class="sxs-lookup"><span data-stu-id="529bb-276">On Windows, the MSI package now installs to the following path:</span></span>

- <span data-ttu-id="529bb-277">`$env:ProgramFiles\PowerShell\6\` для стабильной установки версии 6.x;</span><span class="sxs-lookup"><span data-stu-id="529bb-277">`$env:ProgramFiles\PowerShell\6\` for the stable installation of 6.x</span></span>
- <span data-ttu-id="529bb-278">`$env:ProgramFiles\PowerShell\6-preview\` для установки предварительной версии 6.x.</span><span class="sxs-lookup"><span data-stu-id="529bb-278">`$env:ProgramFiles\PowerShell\6-preview\` for the preview installation of 6.x</span></span>

<span data-ttu-id="529bb-279">Это изменение гарантирует, что PowerShell Core можно обновлять и обслуживать с помощью Центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="529bb-279">This change ensures that PowerShell Core can be updated/serviced by Microsoft Update.</span></span>

<span data-ttu-id="529bb-280">Дополнительные сведения см. в [PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md).</span><span class="sxs-lookup"><span data-stu-id="529bb-280">For more information, check out [PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md).</span></span>

### <a name="telemetry-can-only-be-disabled-with-an-environment-variable"></a><span data-ttu-id="529bb-281">Данные телеметрии можно отключить только с помощью переменной среды</span><span class="sxs-lookup"><span data-stu-id="529bb-281">Telemetry can only be disabled with an environment variable</span></span>

<span data-ttu-id="529bb-282">PowerShell Core отправляет основные данные телеметрии в корпорацию Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="529bb-282">PowerShell Core sends basic telemetry data to Microsoft when it is launched.</span></span> <span data-ttu-id="529bb-283">В эти данные входят имя ОС, версия ОС и версия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-283">The data includes the OS name, OS version, and PowerShell version.</span></span> <span data-ttu-id="529bb-284">Они позволяют нам лучше понимать среды, где используется PowerShell, а также приоритизировать новые функции и исправления.</span><span class="sxs-lookup"><span data-stu-id="529bb-284">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>

<span data-ttu-id="529bb-285">Чтобы отказаться от использования данных телеметрии, задайте для переменной среды `POWERSHELL_TELEMETRY_OPTOUT` значение `true`, `yes` или `1`.</span><span class="sxs-lookup"><span data-stu-id="529bb-285">To opt-out of this telemetry, set the environment variable `POWERSHELL_TELEMETRY_OPTOUT` to `true`, `yes`, or `1`.</span></span> <span data-ttu-id="529bb-286">Мы больше не поддерживаем удаление файла `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` для отключения телеметрии.</span><span class="sxs-lookup"><span data-stu-id="529bb-286">We no longer support deletion of the file `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` to disable telemetry.</span></span>

### <a name="disallowed-basic-auth-over-http-in-powershell-remoting-on-unix-platforms"></a><span data-ttu-id="529bb-287">В системе удаленного взаимодействия PowerShell на платформах Unix запрещена обычная проверка подлинности по протоколу HTTP</span><span class="sxs-lookup"><span data-stu-id="529bb-287">Disallowed Basic Auth over HTTP in PowerShell Remoting on Unix platforms</span></span>

<span data-ttu-id="529bb-288">Чтобы исключить использование незашифрованного трафика, теперь для удаленного взаимодействия PowerShell на платформах Unix требуется использование NTLM или Negotiate либо HTTPS.</span><span class="sxs-lookup"><span data-stu-id="529bb-288">To prevent the use of unencrypted traffic, PowerShell Remoting on Unix platforms now requires usage of NTLM/Negotiate or HTTPS.</span></span>

<span data-ttu-id="529bb-289">Дополнительные сведения об этих изменениях см. в статье [Проблема № 6779](https://github.com/PowerShell/PowerShell/issues/6779).</span><span class="sxs-lookup"><span data-stu-id="529bb-289">For more information on these changes, check out [Issue #6779](https://github.com/PowerShell/PowerShell/issues/6779).</span></span>

### <a name="removed-visualbasic-as-a-supported-language-in-add-type"></a><span data-ttu-id="529bb-290">Удален `VisualBasic` как поддерживаемый язык в Add-Type</span><span class="sxs-lookup"><span data-stu-id="529bb-290">Removed `VisualBasic` as a supported language in Add-Type</span></span>

<span data-ttu-id="529bb-291">Раньше для компиляции кода Visual Basic использовался командлет `Add-Type`.</span><span class="sxs-lookup"><span data-stu-id="529bb-291">In the past, you could compile Visual Basic code using the `Add-Type` cmdlet.</span></span> <span data-ttu-id="529bb-292">Visual Basic редко использовался с `Add-Type`.</span><span class="sxs-lookup"><span data-stu-id="529bb-292">Visual Basic was rarely used with `Add-Type`.</span></span> <span data-ttu-id="529bb-293">Мы удалили эту функцию, чтобы уменьшить размер PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529bb-293">We removed this feature to reduce the size of PowerShell.</span></span>

### <a name="cleaned-up-uses-of-commandtypesworkflow-and-workflowinfocleaned"></a><span data-ttu-id="529bb-294">Отменено использование `CommandTypes.Workflow` и `WorkflowInfoCleaned`</span><span class="sxs-lookup"><span data-stu-id="529bb-294">Cleaned up uses of `CommandTypes.Workflow` and `WorkflowInfoCleaned`</span></span>

<span data-ttu-id="529bb-295">Дополнительные сведения об этих изменениях см. в статье [PR #6708](https://github.com/PowerShell/PowerShell/pull/6708).</span><span class="sxs-lookup"><span data-stu-id="529bb-295">For more information on these changes, check out [PR #6708](https://github.com/PowerShell/PowerShell/pull/6708).</span></span>

### <a name="group-object-now-sorts-the-groups"></a><span data-ttu-id="529bb-296">Командлет Group-Object теперь умеет сортировать группы</span><span class="sxs-lookup"><span data-stu-id="529bb-296">Group-Object now sorts the groups</span></span>

<span data-ttu-id="529bb-297">В рамках оптимизации производительности `Group-Object` возвращает отсортированный список групп.</span><span class="sxs-lookup"><span data-stu-id="529bb-297">As part of the performance improvement, `Group-Object` now returns a sorted listing of the groups.</span></span>
<span data-ttu-id="529bb-298">При этом порядок может быть произвольным, и может оказаться, что это не то, что вам нужно, если вам потребуется первая группа.</span><span class="sxs-lookup"><span data-stu-id="529bb-298">Although you should not rely on the order, you could be broken by this change if you wanted the first group.</span></span> <span data-ttu-id="529bb-299">Мы решили, что это изменение стоит реализовать из-за роста производительности и незначительной зависимости от прежнего поведения командлета.</span><span class="sxs-lookup"><span data-stu-id="529bb-299">We decided that this performance improvement was worth the change since the impact of being dependent on previous behavior is low.</span></span>

<span data-ttu-id="529bb-300">Дополнительные сведения об этом изменении см. в разделе [проблема № 7409](https://github.com/PowerShell/PowerShell/issues/7409).</span><span class="sxs-lookup"><span data-stu-id="529bb-300">For more information on this change, see [Issue #7409](https://github.com/PowerShell/PowerShell/issues/7409).</span></span>

<!-- URL references -->
[Экспериментальные возможности]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[Experimental Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
