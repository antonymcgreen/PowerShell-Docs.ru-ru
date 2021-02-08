---
title: Новые возможности PowerShell 7.1
description: Новые возможности и изменения в PowerShell 7.1
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577213"
---
# <a name="whats-new-in-powershell-71"></a><span data-ttu-id="cacfb-103">Новые возможности PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="cacfb-103">What's New in PowerShell 7.1</span></span>

<span data-ttu-id="cacfb-104">11 ноября 2020 г. мы [объявили](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) о выпуске общедоступной версии PowerShell 7.1.</span><span class="sxs-lookup"><span data-stu-id="cacfb-104">On November 11, 2020 we [announced](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) the general availability of PowerShell 7.1.</span></span> <span data-ttu-id="cacfb-105">Основываясь на фундаменте, заложенном в PowerShell 7.0, мы уделили больше внимания проблемам сообщества и реализовали ряд усовершенствований и исправлений.</span><span class="sxs-lookup"><span data-stu-id="cacfb-105">Building on the foundation established in PowerShell 7.0, our efforts focused on community issues and include a number of improvements and fixes.</span></span> <span data-ttu-id="cacfb-106">Мы стремимся поддерживать высокую стабильность и производительность платформы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cacfb-106">We are committed to ensuring that PowerShell remains a stable and performant platform.</span></span>

<span data-ttu-id="cacfb-107">Ниже перечислены новые функции, обновления и критические изменения в PowerShell 7.1.</span><span class="sxs-lookup"><span data-stu-id="cacfb-107">PowerShell 7.1 includes the following features, updates, and breaking changes.</span></span>

- <span data-ttu-id="cacfb-108">PSReadLine 2.1.0 с прогнозной технологией IntelliSense</span><span class="sxs-lookup"><span data-stu-id="cacfb-108">PSReadLine 2.1.0, which includes Predictive IntelliSense</span></span>
- <span data-ttu-id="cacfb-109">Версия PowerShell 7.1 опубликована в Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="cacfb-109">PowerShell 7.1 has been published to the Microsoft Store</span></span>
- <span data-ttu-id="cacfb-110">Пакеты установщика обновлены для новых версий ОС с поддержкой ARM64.</span><span class="sxs-lookup"><span data-stu-id="cacfb-110">Installer packages updated for new OS versions with support for ARM64</span></span>
- <span data-ttu-id="cacfb-111">4 новые экспериментальные функции; 2 экспериментальные функции стали основными.</span><span class="sxs-lookup"><span data-stu-id="cacfb-111">4 new experimental features and 2 experimental features promoted to mainstream</span></span>
- <span data-ttu-id="cacfb-112">Несколько критических изменений для повышения удобства использования</span><span class="sxs-lookup"><span data-stu-id="cacfb-112">Several breaking changes to improve usability</span></span>

<span data-ttu-id="cacfb-113">Полный список изменений доступен в [журнале изменений](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="cacfb-113">For a complete list of changes, see the [CHANGELOG](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) in the GitHub repository.</span></span>

## <a name="psreadline-210"></a><span data-ttu-id="cacfb-114">PSReadLine 2.1.0</span><span class="sxs-lookup"><span data-stu-id="cacfb-114">PSReadLine 2.1.0</span></span>

<span data-ttu-id="cacfb-115">Кроме того, PowerShell 7.1 включает версию PSReadLine 2.1.0.</span><span class="sxs-lookup"><span data-stu-id="cacfb-115">PowerShell 7.1 also include PSReadLine 2.1.0.</span></span> <span data-ttu-id="cacfb-116">В ней реализована прогнозная технология IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="cacfb-116">This version includes Predictive IntelliSense.</span></span> <span data-ttu-id="cacfb-117">Дополнительные сведения о прогнозной технологии IntelliSense см. в [объявлении](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/), опубликованном в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cacfb-117">For more information about the Predictive IntelliSense feature, see the [announcement](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) in the PowerShell blog.</span></span>

## <a name="microsoft-store-installer-package"></a><span data-ttu-id="cacfb-118">Пакет установщика в Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cacfb-118">Microsoft Store installer package</span></span>

<span data-ttu-id="cacfb-119">Версия PowerShell 7.1 опубликована в Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="cacfb-119">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="cacfb-120">Этот выпуск PowerShell можно найти на веб-сайте [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) или в приложении Store в ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="cacfb-120">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="cacfb-121">Пакет Microsoft Store обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="cacfb-121">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="cacfb-122">автоматические обновления, встроенные в основной механизм Windows 10;</span><span class="sxs-lookup"><span data-stu-id="cacfb-122">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="cacfb-123">интеграция с другими механизмами распространения программного обеспечения, такими как Intune и SCCM.</span><span class="sxs-lookup"><span data-stu-id="cacfb-123">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

> [!NOTE]
> <span data-ttu-id="cacfb-124">Параметры конфигурации системного уровня, хранящиеся в `$PSHOME`, нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="cacfb-124">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="cacfb-125">Это относится и к конфигурации WSMAN.</span><span class="sxs-lookup"><span data-stu-id="cacfb-125">This includes the WSMAN configuration.</span></span> <span data-ttu-id="cacfb-126">Это означает, что вы не сможете подключать удаленные сеансы к установкам PowerShell на основе хранилища.</span><span class="sxs-lookup"><span data-stu-id="cacfb-126">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="cacfb-127">Поддерживаются конфигурации уровня пользователя и удаленное взаимодействие по SSH.</span><span class="sxs-lookup"><span data-stu-id="cacfb-127">User-level configurations and SSH remoting are supported.</span></span>

## <a name="other-installers"></a><span data-ttu-id="cacfb-128">Другие установщики</span><span class="sxs-lookup"><span data-stu-id="cacfb-128">Other installers</span></span>

<span data-ttu-id="cacfb-129">Более актуальные сведения о поддерживаемых операционных системах и жизненном цикле поддержки см. в статье [Жизненный цикл поддержки PowerShell](/powershell/scripting/powershell-support-lifecycle).</span><span class="sxs-lookup"><span data-stu-id="cacfb-129">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

<span data-ttu-id="cacfb-130">Обратитесь к инструкциям по установке для своей операционной системы:</span><span class="sxs-lookup"><span data-stu-id="cacfb-130">Check the installation instructions for your preferred operating system:</span></span>

- [<span data-ttu-id="cacfb-131">Windows</span><span class="sxs-lookup"><span data-stu-id="cacfb-131">Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows)
- [<span data-ttu-id="cacfb-132">macOS</span><span class="sxs-lookup"><span data-stu-id="cacfb-132">macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos)
- [<span data-ttu-id="cacfb-133">Linux</span><span class="sxs-lookup"><span data-stu-id="cacfb-133">Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux)

<span data-ttu-id="cacfb-134">Кроме того, PowerShell 7.1 поддерживает выпуски Debian и Ubuntu для ARM32 и ARM64, а также Alpine Linux для ARM64.</span><span class="sxs-lookup"><span data-stu-id="cacfb-134">Additionally, PowerShell 7.1 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="cacfb-135">Сообщество также предоставило пакеты для [Arch](https://aur.archlinux.org/packages/powershell/) и Kali Linux, хотя они не поддерживаются официально.</span><span class="sxs-lookup"><span data-stu-id="cacfb-135">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="cacfb-136">Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine и ARM сейчас не поддерживают удаленное взаимодействие WinRM.</span><span class="sxs-lookup"><span data-stu-id="cacfb-136">Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine and Arm currently do not support WinRM remoting.</span></span> <span data-ttu-id="cacfb-137">Подробные сведения о настройке удаленного взаимодействия на основе SSH см. в статье [Удаленное взаимодействие с PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="cacfb-137">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="experimental-features"></a><span data-ttu-id="cacfb-138">Экспериментальные возможности</span><span class="sxs-lookup"><span data-stu-id="cacfb-138">Experimental Features</span></span>

<span data-ttu-id="cacfb-139">Дополнительные сведения см. в статье об [использовании экспериментальных функций](../learn/experimental-features.md).</span><span class="sxs-lookup"><span data-stu-id="cacfb-139">For more information about the Experimental Features, see [Using Experimental Features](../learn/experimental-features.md).</span></span>

<span data-ttu-id="cacfb-140">В этом выпуске следующие экспериментальные функции стали основными:</span><span class="sxs-lookup"><span data-stu-id="cacfb-140">The following experimental features are now mainstream features in this release:</span></span>

- [<span data-ttu-id="cacfb-141">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="cacfb-141">PSNullConditionalOperators</span></span>](../learn/experimental-features.md#psnullconditionaloperators)
- [<span data-ttu-id="cacfb-142">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="cacfb-142">PSUnixFileStat</span></span>](../learn/experimental-features.md#psunixfilestat)

<span data-ttu-id="cacfb-143">В этом выпуске были добавлены следующие экспериментальные функции:</span><span class="sxs-lookup"><span data-stu-id="cacfb-143">The following experimental features were added in this release:</span></span>

- [<span data-ttu-id="cacfb-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="cacfb-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - <span data-ttu-id="cacfb-145">В PowerShell 7.1 эта экспериментальная функция расширена: ко всем командлетам `*-PSBreakpoint` добавлен параметр **Runspace**.</span><span class="sxs-lookup"><span data-stu-id="cacfb-145">PowerShell 7.1 extends this experimental feature to add the **Runspace** parameter to all `*-PSBreakpoint` cmdlets.</span></span> <span data-ttu-id="cacfb-146">Параметр **Runspace** указывает объекту **Runspace** взаимодействовать с точками останова в указанном пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="cacfb-146">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

- <span data-ttu-id="cacfb-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) — эта функция позволяет передавать пути к поставщикам PowerShell в собственные команды, которые не поддерживают синтаксис путей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cacfb-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) - This feature allows you to pass PowerShell provider paths to native commands that don't support PowerShell path syntax.</span></span>

- <span data-ttu-id="cacfb-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) — когда левый операнд в инструкции оператора `-replace` не является строкой, он преобразуется в строку.</span><span class="sxs-lookup"><span data-stu-id="cacfb-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) - When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span> <span data-ttu-id="cacfb-149">Когда эта функция включена, при преобразовании строк не используются настройки языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="cacfb-149">With the feature enabled, the conversion does not use Culture settings for string conversion.</span></span>

- <span data-ttu-id="cacfb-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) — основа для поддержки будущих подключаемых модулей с прогнозной технологией IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="cacfb-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) lays the groundwork to support future Predictive IntelliSense plug-ins.</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="cacfb-151">Критические изменения и улучшения</span><span class="sxs-lookup"><span data-stu-id="cacfb-151">Breaking Changes and Improvements</span></span>

- <span data-ttu-id="cacfb-152">Исправлено ошибочное значение `$false` для `$?` при записи собственной команды в `stderr` ([#13395](https://github.com/PowerShell/PowerShell/pull/13395)).</span><span class="sxs-lookup"><span data-stu-id="cacfb-152">Fix `$?` to not be `$false` when native command writes to `stderr` ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))</span></span>

  <span data-ttu-id="cacfb-153">Обычно, когда собственные команды выполняют запись в `stderr`, им не нужно сообщать об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cacfb-153">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="cacfb-154">В результате этого изменения `$?` задается равным `$false` только в том случае, если собственная команда имеет ненулевой код выхода.</span><span class="sxs-lookup"><span data-stu-id="cacfb-154">With this change `$?` is set to `$false` only when the native command also has a non-zero exit code.</span></span> <span data-ttu-id="cacfb-155">Это изменение не связано с экспериментальной функцией `PSNotApplyErrorActionToStderr`.</span><span class="sxs-lookup"><span data-stu-id="cacfb-155">This change is unrelated to the experimental feature `PSNotApplyErrorActionToStderr`.</span></span>

- <span data-ttu-id="cacfb-156">Теперь `$ErrorActionPreference` не влияет на выходные данные `stderr` собственных команд ([#13361](https://github.com/PowerShell/PowerShell/pull/13361)).</span><span class="sxs-lookup"><span data-stu-id="cacfb-156">Make `$ErrorActionPreference` not affect `stderr` output of native commands ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))</span></span>

  <span data-ttu-id="cacfb-157">Обычно, когда собственные команды выполняют запись в `stderr`, им не нужно сообщать об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cacfb-157">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="cacfb-158">В результате этого изменения выходные данные `stderr` по-прежнему фиксируются в объектах **ErrorRecord**, но среда выполнения больше не применяет `$ErrorActionPreference`, если **ErrorRecord** поступает от собственной команды.</span><span class="sxs-lookup"><span data-stu-id="cacfb-158">With this change, `stderr` output is still captured in **ErrorRecord** objects, but the runtime no longer applies `$ErrorActionPreference` if the **ErrorRecord** comes from a native command.</span></span>

- <span data-ttu-id="cacfb-159">Параметр `-FromUnixTime` переименован в `-UnixTimeSeconds` в `Get-Date`, чтобы разрешить ввод времени в формате Unix ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (отдельная благодарность @aetos382!).</span><span class="sxs-lookup"><span data-stu-id="cacfb-159">Rename `-FromUnixTime` to `-UnixTimeSeconds` on `Get-Date` to allow Unix time input ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (Thanks @aetos382!)</span></span>

  <span data-ttu-id="cacfb-160">Параметр `-FromUnixTime` был добавлен в версии 7.1-preview.2.</span><span class="sxs-lookup"><span data-stu-id="cacfb-160">The `-FromUnixTime` parameter was added during 7.1-preview.2.</span></span> <span data-ttu-id="cacfb-161">Он был переименован, чтобы лучше соответствовать типу данных.</span><span class="sxs-lookup"><span data-stu-id="cacfb-161">The parameter was renamed to better match the data type.</span></span> <span data-ttu-id="cacfb-162">Этот параметр принимает целочисленное значение, которое представляет время в секундах с 0:00:00 1 января 1970 г.</span><span class="sxs-lookup"><span data-stu-id="cacfb-162">This parameter takes an integer value that represents in seconds since January 1, 1970, 0:00:00.</span></span>

  <span data-ttu-id="cacfb-163">В этом примере время в формате Unix (представленное количеством секунд с 0:00:00 01.01.1970) преобразуется в тип DateTime.</span><span class="sxs-lookup"><span data-stu-id="cacfb-163">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- <span data-ttu-id="cacfb-164">Разрешено переопределять явно заданным именованным параметром аналогичный параметр из сплаттинга хэш-таблицы (#13162)</span><span class="sxs-lookup"><span data-stu-id="cacfb-164">Allow explicitly specified named parameter to supersede the same one from hashtable splatting (#13162)</span></span>

  <span data-ttu-id="cacfb-165">В результате этого изменения именованные параметры, передаваемые через сплаттинг, перемещаются в конец списка параметров, так что они привязываются после привязки всех явно указанных именованных параметров.</span><span class="sxs-lookup"><span data-stu-id="cacfb-165">With this change, the named parameters from splatting are moved to the end of the parameter list so that they are bound after all explicitly specified named parameters are bound.</span></span> <span data-ttu-id="cacfb-166">При привязке параметров в простых функциях не возникает ошибка, если не удается найти указанный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="cacfb-166">Parameter binding for simple functions doesn't throw an error when a specified named parameter cannot be found.</span></span> <span data-ttu-id="cacfb-167">Неизвестные именованные параметры привязываются к параметру `$args` простой функции.</span><span class="sxs-lookup"><span data-stu-id="cacfb-167">Unknown named parameters are bound to the `$args` parameter of the simple function.</span></span> <span data-ttu-id="cacfb-168">Перемещение сплаттинга в конец списка аргументов приводит к изменению порядка, в котором параметры следуют в `$args`.</span><span class="sxs-lookup"><span data-stu-id="cacfb-168">Moving splatting to the end of the argument list changes the order the parameters appears in `$args`.</span></span>

  <span data-ttu-id="cacfb-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="cacfb-169">For example:</span></span>

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  <span data-ttu-id="cacfb-170">В предыдущем случае аргумент **MyPath** не привязан к `-Path`, так как он является третьим в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="cacfb-170">In the previous behavior, **MyPath** is not bound to `-Path` because it's the third argument in the argument list.</span></span> <span data-ttu-id="cacfb-171">## В результате он помещается в '$args' вместе с `Blah = "World"`</span><span class="sxs-lookup"><span data-stu-id="cacfb-171">## So it ends up being stuffed into '$args' along with `Blah = "World"`</span></span>

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  <span data-ttu-id="cacfb-172">В результате этого изменения аргументы из `@hash` перемещаются в конец списка аргументов.</span><span class="sxs-lookup"><span data-stu-id="cacfb-172">With this change, the arguments from `@hash` are moved to the end of the argument list.</span></span> <span data-ttu-id="cacfb-173">**MyPath** становится первым аргументом в списке, поэтому он привязывается к `-Path`.</span><span class="sxs-lookup"><span data-stu-id="cacfb-173">**MyPath** becomes the first argument in the list, so it is bound to `-Path`.</span></span>

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- <span data-ttu-id="cacfb-174">Параметр переключателя `-Qualifier` теперь не зависит от позиции в `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (отдельная благодарность @yecril71pl!).</span><span class="sxs-lookup"><span data-stu-id="cacfb-174">Make the switch parameter `-Qualifier` not positional for `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (Thanks @yecril71pl!)</span></span>

- <span data-ttu-id="cacfb-175">Рабочий каталог разрешается для `Start-Process` как литеральный путь, если он не указан ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (отдельная благодарность @NoMoreFood!).</span><span class="sxs-lookup"><span data-stu-id="cacfb-175">Resolve the working directory as literal path for `Start-Process` when it's not specified ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (Thanks @NoMoreFood!)</span></span>

- <span data-ttu-id="cacfb-176">Параметр `-OutFile` теперь ведет себя в веб-командлетах как `-LiteralPath` ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (отдельная благодарность @iSazonov!).</span><span class="sxs-lookup"><span data-stu-id="cacfb-176">Make `-OutFile` parameter in web cmdlets to work like `-LiteralPath` ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="cacfb-177">Исправлена привязка параметра строки для числовых литералов `BigInteger` ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (отдельная благодарность @vexx32!).</span><span class="sxs-lookup"><span data-stu-id="cacfb-177">Fix string parameter binding for `BigInteger` numeric literals ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (Thanks @vexx32!)</span></span>

- <span data-ttu-id="cacfb-178">В Windows `Start-Process` позволяет создать среду процесса со всеми переменными среды из текущего сеанса, а при использовании `-UseNewEnvironment` создается новая среда процесса по умолчанию ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (отдельная благодарность @iSazonov!).</span><span class="sxs-lookup"><span data-stu-id="cacfb-178">On Windows, `Start-Process` creates a process environment with all the environment variables from current session, using `-UseNewEnvironment` creates a new default process environment ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="cacfb-179">Устранен перенос возвращаемого результата в `PSObject` при преобразовании `ScriptBlock` в делегат ([#10619](https://github.com/PowerShell/PowerShell/pull/10619)).</span><span class="sxs-lookup"><span data-stu-id="cacfb-179">Do not wrap return result in `PSObject` when converting a `ScriptBlock` to a delegate ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))</span></span>

  <span data-ttu-id="cacfb-180">Когда `ScriptBlock` преобразуется в тип делегата для использования в контексте C#, перенос результата в `PSObject` приводит к ненужным проблемам.</span><span class="sxs-lookup"><span data-stu-id="cacfb-180">When a `ScriptBlock` is converted to a delegate type to be used in C# context, wrapping the result in a `PSObject` brings unneeded troubles:</span></span>

  - <span data-ttu-id="cacfb-181">Когда значение преобразуется в возвращаемый тип-делегат, `PSObject` по сути разворачивается.</span><span class="sxs-lookup"><span data-stu-id="cacfb-181">When the value is converted to the delegate return type, the `PSObject` essentially gets unwrapped.</span></span> <span data-ttu-id="cacfb-182">Поэтому `PSObject` не требуется.</span><span class="sxs-lookup"><span data-stu-id="cacfb-182">So the `PSObject` is unneeded.</span></span>
  - <span data-ttu-id="cacfb-183">Если возвращаемый тип-делегат — `object`, он переносится в `PSObject`, что затрудняет работу с ним в коде C#.</span><span class="sxs-lookup"><span data-stu-id="cacfb-183">When the delegate return type is `object`, it gets wrapped in a `PSObject` making it hard to work with in C# code.</span></span>

  <span data-ttu-id="cacfb-184">В результате этого изменения возвращается базовый объект.</span><span class="sxs-lookup"><span data-stu-id="cacfb-184">After this change, the returned object is the underlying object.</span></span>
