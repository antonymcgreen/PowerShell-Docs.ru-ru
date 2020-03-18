---
title: Новые возможности PowerShell 7.0
description: Новые возможности и изменения в PowerShell 7.0
ms.date: 03/04/2020
ms.openlocfilehash: 6915bb70d6e54da86d2b935e3feed8d7f3770ba9
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78404988"
---
# <a name="whats-new-in-powershell-70"></a><span data-ttu-id="ec4a2-103">Новые возможности PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="ec4a2-103">What's New in PowerShell 7.0</span></span>

<span data-ttu-id="ec4a2-104">PowerShell 7.0 — это кроссплатформенный (Windows, macOS и Linux) выпуск PowerShell с открытым кодом, который предназначен для управления разнородными средами и гибридным облаком.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-104">PowerShell 7.0 is an open-source, cross-platform (Windows, macOS, and Linux) edition of PowerShell, built to manage heterogeneous environments and hybrid cloud.</span></span>

<span data-ttu-id="ec4a2-105">В этом выпуске был добавлен ряд новых возможностей, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-105">In this release, we're introducing a number of new features, including:</span></span>

- <span data-ttu-id="ec4a2-106">параллелизация конвейера с помощью `ForEach-Object -Parallel`;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-106">Pipeline parallelization with `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="ec4a2-107">новые операторы:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-107">New operators:</span></span>
  - <span data-ttu-id="ec4a2-108">тернарный оператор `a ? b : c`;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-108">Ternary operator: `a ? b : c`</span></span>
  - <span data-ttu-id="ec4a2-109">операторы сцепления конвейеров `||` и `&&`;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-109">Pipeline chain operators: `||` and `&&`</span></span>
  - <span data-ttu-id="ec4a2-110">условные операторы со значением NULL `??` и `??=`;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-110">Null conditional operators: `??` and `??=`</span></span>
- <span data-ttu-id="ec4a2-111">упрощенное динамическое представление ошибок и командлет `Get-Error` для более легкого анализа ошибок;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-111">A simplified and dynamic error view and `Get-Error` cmdlet for easier investigation of errors</span></span>
- <span data-ttu-id="ec4a2-112">уровень совместимости, позволяющий пользователям импортировать модули в рамках неявного сеанса Windows PowerShell;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-112">A compatibility layer that enables users to import modules in an implicit Windows PowerShell session</span></span>
- <span data-ttu-id="ec4a2-113">автоматические уведомления о новых версиях;</span><span class="sxs-lookup"><span data-stu-id="ec4a2-113">Automatic new version notifications</span></span>
- <span data-ttu-id="ec4a2-114">возможность вызывать ресурсы DSC непосредственно из PowerShell 7 (экспериментальная функция).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-114">The ability to invoke DSC resources directly from PowerShell 7 (experimental)</span></span>

<span data-ttu-id="ec4a2-115">Полный список возможностей и исправлений см. в [журналах изменений](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-115">To see a full list of features and fixes, see the [changelogs](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span></span>

## <a name="where-can-i-install-powershell"></a><span data-ttu-id="ec4a2-116">Где можно установить PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ec4a2-116">Where can I install PowerShell?</span></span>

<span data-ttu-id="ec4a2-117">PowerShell 7 в настоящее время поддерживает следующие 64-разрядные операционные системы.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-117">PowerShell 7 currently supports the following operating systems on x64, including:</span></span>

- <span data-ttu-id="ec4a2-118">Windows 8.1 и 10</span><span class="sxs-lookup"><span data-stu-id="ec4a2-118">Windows 8.1, and 10</span></span>
- <span data-ttu-id="ec4a2-119">Windows Server 2012, 2012 R2, 2016 и 2019</span><span class="sxs-lookup"><span data-stu-id="ec4a2-119">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>
- <span data-ttu-id="ec4a2-120">macOS 10.13 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ec4a2-120">macOS 10.13+</span></span>
- <span data-ttu-id="ec4a2-121">Red Hat Enterprise Linux (RHEL) и CentOS 7</span><span class="sxs-lookup"><span data-stu-id="ec4a2-121">Red Hat Enterprise Linux (RHEL) / CentOS 7</span></span>
- <span data-ttu-id="ec4a2-122">Fedora 30 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ec4a2-122">Fedora 30+</span></span>
- <span data-ttu-id="ec4a2-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="ec4a2-123">Debian 9</span></span>
- <span data-ttu-id="ec4a2-124">Ubuntu LTS 16.04 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ec4a2-124">Ubuntu LTS 16.04+</span></span>
- <span data-ttu-id="ec4a2-125">Alpine Linux 3.8 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ec4a2-125">Alpine Linux 3.8+</span></span>

<span data-ttu-id="ec4a2-126">Кроме того, PowerShell 7.0 поддерживает выпуски Debian и Ubuntu для ARM32 и ARM64, а также Alpine Linux для ARM64.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-126">Additionally, PowerShell 7.0 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="ec4a2-127">Обратитесь к инструкциям по установке для вашей операционной системы: [Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7) или [Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-127">Check the installation instructions for your preferred operating system [Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7), or [Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7).</span></span>

<span data-ttu-id="ec4a2-128">Сообщество также предоставило пакеты для [Arch](https://aur.archlinux.org/packages/powershell/) и Kali Linux, хотя они не поддерживаются официально.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-128">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-129">В настоящее время Debian 10 и CentOS 8 не поддерживают удаленное взаимодействие WinRM.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-129">Debian 10 and CentOS 8 currently do not support WinRM remoting.</span></span> <span data-ttu-id="ec4a2-130">Подробные сведения о настройке удаленного взаимодействия на основе SSH см. в статье [Удаленное взаимодействие с PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-130">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7).</span></span>

<span data-ttu-id="ec4a2-131">Более актуальные сведения о поддерживаемых операционных системах и жизненном цикле поддержки см. в статье [Жизненный цикл поддержки PowerShell](/powershell/scripting/powershell-support-lifecycle?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-131">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle?view=powershell-7).</span></span>

## <a name="running-powershell-7"></a><span data-ttu-id="ec4a2-132">Запуск PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="ec4a2-132">Running PowerShell 7</span></span>

<span data-ttu-id="ec4a2-133">PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-133">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="ec4a2-134">Для PowerShell Core 6.x версия PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-134">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>

- <span data-ttu-id="ec4a2-135">PowerShell 7 устанавливается в папке `%programfiles%\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-135">PowerShell 7 is installed to `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="ec4a2-136">Папка `%programfiles%\PowerShell\7` добавляется в переменную `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-136">The `%programfiles%\PowerShell\7` folder is added to `$env:PATH`</span></span>

<span data-ttu-id="ec4a2-137">Пакеты установщика PowerShell 7 обновляют предыдущие версии PowerShell Core 6.x.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-137">The PowerShell 7 installer packages upgrade previous versions of PowerShell Core 6.x:</span></span>

- <span data-ttu-id="ec4a2-138">PowerShell Core 6.x в Windows: каталог `%programfiles%\PowerShell\6` заменяется каталогом `%programfiles%\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-138">PowerShell Core 6.x on Windows: `%programfiles%\PowerShell\6` is replaced by `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="ec4a2-139">Linux: каталог `/opt/microsoft/powershell/6` заменяется каталогом `/opt/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-139">Linux: `/opt/microsoft/powershell/6` is replaced by `/opt/microsoft/powershell/7`</span></span>
- <span data-ttu-id="ec4a2-140">macOS: каталог `/usr/local/microsoft/powershell/6` заменяется каталогом `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-140">macOS: `/usr/local/microsoft/powershell/6` is replaced by `/usr/local/microsoft/powershell/7`</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-141">В Windows PowerShell исполняемый файл для запуска PowerShell называется `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-141">In Windows PowerShell, the executable to launch PowerShell is named `powershell.exe`.</span></span> <span data-ttu-id="ec4a2-142">В версии 6 и более поздних имя исполняемого файла было изменено для поддержки параллельного выполнения.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-142">In version 6 and above, the executable is changed to support side-by-side execution.</span></span> <span data-ttu-id="ec4a2-143">Новый исполняемый файл для запуска PowerShell 7 называется `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-143">The new executable to launch PowerShell 7 is `pwsh.exe`.</span></span> <span data-ttu-id="ec4a2-144">Предварительные сборки сохраняются как `pwsh-preview` (а не `pwsh`) в каталоге 7-preview.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-144">Preview builds will remain in-place as `pwsh-preview` instead of `pwsh` under the 7-preview directory.</span></span>

## <a name="improved-backwards-compatibility-with-windows-powershell"></a><span data-ttu-id="ec4a2-145">Улучшенная обратная совместимость с Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec4a2-145">Improved backwards compatibility with Windows PowerShell</span></span>

<span data-ttu-id="ec4a2-146">Выпуск PowerShell 7.0 знаменует переход на .NET Core 3.1, благодаря чему обеспечивается значительно более полная обратная совместимость с существующими модулями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-146">PowerShell 7.0 marks a move a to .NET Core 3.1, enabling significantly more backwards compatibility with existing Windows PowerShell modules.</span></span> <span data-ttu-id="ec4a2-147">Это относится ко многим модулям в Windows, которым требуются возможности графического пользовательского интерфейса, таким как `Out-GridView` и `Show-Command`, а также ко многим модулям управления ролями, поставляемым с Windows.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-147">This includes many modules on Windows that require GUI functionality like `Out-GridView` and `Show-Command`, as well as many role management modules that ship as part of Windows.</span></span>

<span data-ttu-id="ec4a2-148">В Windows для командлета `Import-Module` добавлен новый параметр **UseWindowsPowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-148">For Windows, a new switch parameter **UseWindowsPowerShell** is added to `Import-Module`.</span></span> <span data-ttu-id="ec4a2-149">Он создает модуль прокси в PowerShell 7, который использует локальный процесс Windows PowerShell для неявного выполнения командлетов, содержащихся в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-149">This switch creates a proxy module in PowerShell 7 that uses a local Windows PowerShell process to implicitly run any cmdlets contained in that module.</span></span> <span data-ttu-id="ec4a2-150">Дополнительные сведения см. в статье [Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-150">For more information on [Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7).</span></span>

<span data-ttu-id="ec4a2-151">Дополнительные сведения о модулях Майкрософт, работающих с PowerShell 7.0, см. в [таблице совместимости модулей](https://aka.ms/PSModuleCompat).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-151">For more information on which Microsoft modules work with PowerShell 7.0, see the [Module Compatibility Table](https://aka.ms/PSModuleCompat).</span></span>

## <a name="parallel-execution-added-to-foreach-object"></a><span data-ttu-id="ec4a2-152">Поддержка параллельного выполнения для ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="ec4a2-152">Parallel execution added to ForEach-Object</span></span>

<span data-ttu-id="ec4a2-153">Командлет `ForEach-Object`, который перебирает элементы в коллекции, теперь имеет встроенную поддержку параллелизма благодаря новому параметру **Parallel**.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-153">The `ForEach-Object` cmdlet, which iterates items in a collection, now has built-in parallelism with the new **Parallel** parameter.</span></span>

<span data-ttu-id="ec4a2-154">По умолчанию параллельные блоки скриптов используют текущий рабочий каталог вызывающего объекта, который запустил параллельные задачи.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-154">By default, parallel script blocks use the current working directory of the caller that started the parallel tasks.</span></span>

<span data-ttu-id="ec4a2-155">В этом примере извлекаются 50 000 записей из пяти системных журналов на локальном компьютере Windows:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-155">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine:</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count

50000
```

<span data-ttu-id="ec4a2-156">С помощью параметра **Parallel** для каждого входного имени журнала указывается блок скрипта, который выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-156">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span>

<span data-ttu-id="ec4a2-157">Новый параметр **ThrottleLimit** ограничивает количество блоков скриптов, выполняющихся параллельно в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-157">The new **ThrottleLimit** parameter limits the number of script blocks running in parallel at a given time.</span></span> <span data-ttu-id="ec4a2-158">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-158">The default is 5.</span></span>

<span data-ttu-id="ec4a2-159">Используйте переменную `$_` для представления текущего входного объекта в блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-159">Use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="ec4a2-160">Используйте область `$using:` для передачи ссылок на переменные в выполняемый блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-160">Use the `$using:` scope to pass variable references to the running script block.</span></span>

<span data-ttu-id="ec4a2-161">См. дополнительные сведения о командлете [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-161">For more information about [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7).</span></span>

## <a name="ternary-operator"></a><span data-ttu-id="ec4a2-162">Тернарный оператор</span><span class="sxs-lookup"><span data-stu-id="ec4a2-162">Ternary operator</span></span>

<span data-ttu-id="ec4a2-163">В PowerShell 7.0 появился тернарный оператор, который работает как упрощенный оператор `if-else`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-163">PowerShell 7.0 introduces a ternary operator which behaves like a simplified `if-else` statement.</span></span>
<span data-ttu-id="ec4a2-164">Тернарный оператор в PowerShell был создан во многом по образцу синтаксиса тернарного оператора в C#:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-164">PowerShell's ternary operator is closely modeled from the C# ternary operator syntax:</span></span>

```
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="ec4a2-165">Условие-выражение оценивается всегда, и его результат преобразуется в **логический** тип для определения того, какая ветвь будет оцениваться далее.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-165">The condition-expression is always evaluated and its result converted to a **Boolean** to determine which branch is evaluated next:</span></span>

- <span data-ttu-id="ec4a2-166">Выражение `<if-true>` выполняется, если выражение `<condition>` имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-166">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="ec4a2-167">Выражение `<if-false>` выполняется, если выражение `<condition>` имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-167">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="ec4a2-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-168">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="ec4a2-169">В этом примере, если путь существует, выводится сообщение **Path exists** (Путь существует).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-169">In this example, if the path exists, then **Path exists** is displayed.</span></span> <span data-ttu-id="ec4a2-170">Если путь не существует, выводится сообщение **Path not found** (Путь не найден).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-170">If the path does not exist, then **Path not found** is displayed.</span></span>

<span data-ttu-id="ec4a2-171">Дополнительные сведения см. в статье об [операторе If](/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-171">For more information [About If](/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7).</span></span>

## <a name="pipeline-chain-operators"></a><span data-ttu-id="ec4a2-172">Операторы сцепления конвейеров</span><span class="sxs-lookup"><span data-stu-id="ec4a2-172">Pipeline chain operators</span></span>

<span data-ttu-id="ec4a2-173">В PowerShell 7 реализованы операторы `&&` и `||` для условного сцепления конвейеров.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-173">PowerShell 7 implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="ec4a2-174">Они называются в PowerShell операторами сцепления конвейеров и похожи на списки И и ИЛИ в таких оболочках, как **Bash** и **Zsh**, а также на символы условной обработки в командной оболочке Windows Shell (**cmd.exe**).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-174">These operators are known in PowerShell as "pipeline chain operators", and are similar to AND and OR lists in shells like **Bash** and **Zsh**, as well as conditional processing symbols in the Windows Command Shell (**cmd.exe**).</span></span>

<span data-ttu-id="ec4a2-175">Оператор `&&` выполняет конвейер в правой части, если конвейер в левой части был выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-175">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="ec4a2-176">И наоборот, оператор `||` выполняет конвейер в правой части, если конвейер в левой части не удалось выполнить.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-176">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-177">Для определения того, был ли выполнен конвейер, эти операторы используют переменные `$?` и `$LASTEXITCODE`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-177">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="ec4a2-178">Это позволяет использовать их с собственными командами, а не только с командлетами или функциями.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-178">This allows you to use them with native commands and not just with cmdlets or functions.</span></span>

<span data-ttu-id="ec4a2-179">В этом примере первая команда завершается успешно и выполняется вторая команда:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-179">Here, the first command succeeds and the second command is executed:</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

<span data-ttu-id="ec4a2-180">В этом примере первую команду выполнить не удается и вторая команда не выполняется:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-180">Here, the first command fails, the second is not executed:</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

<span data-ttu-id="ec4a2-181">В этом примере первая команда завершается успешно и вторая команда не выполняется:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-181">Here, the first command succeeds, the second command is not executed:</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

<span data-ttu-id="ec4a2-182">В этом примере первую команду выполнить не удается, поэтому вторая команда выполняется:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-182">Here, the first command fails, so the second command is executed:</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error 'Bad'
Second
```

<span data-ttu-id="ec4a2-183">См. дополнительные сведения об [операторах сцепления конвейеров](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-183">For more information [About Pipeline Chain Operators](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7).</span></span>

## <a name="null-coalescing-assignment-and-conditional-operators"></a><span data-ttu-id="ec4a2-184">Операторы объединения со значением NULL, присваивания значения NULL и условные операторы со значением NULL</span><span class="sxs-lookup"><span data-stu-id="ec4a2-184">Null-coalescing, assignment, and conditional operators</span></span>

<span data-ttu-id="ec4a2-185">В PowerShell 7 имеются оператор объединения со значением NULL `??`, оператор условного присваивания значения NULL `??=` и операторы доступа к членам, определяемого условием NULL: `?.` и `?[]`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-185">PowerShell 7 includes Null coalescing operator `??`, Null conditional assignment `??=`, and Null conditional member access operators `?.` and `?[]`.</span></span>

### <a name="null-coalescing-operator-"></a><span data-ttu-id="ec4a2-186">Оператор объединения со значением NULL ??</span><span class="sxs-lookup"><span data-stu-id="ec4a2-186">Null-coalescing Operator ??</span></span>

<span data-ttu-id="ec4a2-187">Оператор объединения со значением NULL `??` возвращает значение левого операнда, если оно не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-187">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span>
<span data-ttu-id="ec4a2-188">В противном случае он вычисляет правый операнд и возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-188">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="ec4a2-189">Оператор `??` не вычисляет правый операнд, если значение левого операнда отлично от NULL.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-189">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
100
```

<span data-ttu-id="ec4a2-190">В следующем примере правый операнд не вычисляется:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-190">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-assignment-operator-"></a><span data-ttu-id="ec4a2-191">Оператор условного присваивания значения NULL ??=</span><span class="sxs-lookup"><span data-stu-id="ec4a2-191">Null conditional assignment operator ??=</span></span>

<span data-ttu-id="ec4a2-192">Оператор условного присваивания значения NULL `??=` присваивает значение правого операнда левому операнду только в том случае, если левый операнд имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-192">The null conditional assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="ec4a2-193">Оператор `??=` не вычисляет правый операнд, если значение левого операнда отлично от NULL.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-193">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
100
```

<span data-ttu-id="ec4a2-194">В следующем примере правый операнд не вычисляется:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-194">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-member-access-operators--and--experimental"></a><span data-ttu-id="ec4a2-195">Операторы доступа к членам, определяемого условием NULL: ?.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-195">Null conditional member access operators ?.</span></span> <span data-ttu-id="ec4a2-196">и ?[] (экспериментальная функция)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-196">and ?[] (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-197">Это экспериментальная функция под названием **PSNullConditionalOperators**.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-197">This is an experimental feature named **PSNullConditionalOperators**.</span></span> <span data-ttu-id="ec4a2-198">См. дополнительные сведения об [экспериментальных функциях](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-198">Learn more [About Experimental Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span></span>

<span data-ttu-id="ec4a2-199">Условный оператор со значением NULL разрешает доступ к операнду, являющемуся членом (`?.`) или элементом (`?[]`), только если значение операнда отлично от NULL. В противном случае он возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-199">A null conditional operator permits member access, `?.`, or element access, `?[]`, to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-200">Так как в PowerShell символ `?` может быть частью имени переменной, для использования этих операторов требуется формальное указание имени переменной.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-200">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="ec4a2-201">Поэтому имена переменных необходимо заключать в фигурные скобки `{}`, например `${a}`, в том числе если имена содержат символ `?`: `${a?}`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-201">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="ec4a2-202">В следующем примере возвращается значение свойства члена **Status**:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-202">In the following example, the value of the member property **Status** is returned:</span></span>

```powershell
$Service = Get-Service -Name 'bits'
${Service}?.status
Stopped
```

<span data-ttu-id="ec4a2-203">В следующем примере возвращается значение NULL без попытки доступа к члену **Status**:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-203">The following example will return null, without trying to access the member name **Status**:</span></span>

```powershell
$service = $Null
${Service}?.status
```

<span data-ttu-id="ec4a2-204">Аналогичным образом при использовании оператора `?[]` возвращается значение элемента:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-204">Similarly, using `?[]`, the value of the element will be returned:</span></span>

```powershell
$a = 1..10
${a}?[0]
1
```

<span data-ttu-id="ec4a2-205">Если операнд имеет значение NULL, доступ к элементу не производится и возвращается значение NULL:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-205">And when the operand is null, the element isn't accessed and null is returned:</span></span>

```powershell
$a = $null
${a}?[0]
```

<span data-ttu-id="ec4a2-206">См. дополнительные сведения об [операторах](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-206">For more information [About_Operators](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7).</span></span>

## <a name="new-view-conciseview-and-cmdlet-get-error"></a><span data-ttu-id="ec4a2-207">Новое представление ConciseView и командлет Get-Error</span><span class="sxs-lookup"><span data-stu-id="ec4a2-207">New view ConciseView and cmdlet Get-Error</span></span>

<span data-ttu-id="ec4a2-208">Новое представление **ConciseView**, используемое по умолчанию, улучшает отображение сообщений об ошибках интерактивных функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-208">The display of error messages has been improved to enhance the readability of interactive and script errors with a new default view **ConciseView**.</span></span> <span data-ttu-id="ec4a2-209">Пользователь может выбирать представление с помощью привилегированной переменной `$ErrorView`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-209">The views are user-selectable through the preference variable `$ErrorView`.</span></span>

<span data-ttu-id="ec4a2-210">Если ошибка возникла не в скрипте и не в средстве синтаксического анализа, то в представлении **ConciseView** сообщение о ней выводится в одной строке:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-210">With **ConciseView**, if an error is not from a script or parser error, then it's a single line error message:</span></span>

```powershell
Get-Childitem -Path c:\NotReal
```

```Output
Get-ChildItem: Cannot find path 'C:\NotReal' because it does not exist
```

<span data-ttu-id="ec4a2-211">Если ошибка возникла во время выполнения скрипта или синтаксического анализа, в PowerShell возвращается многострочное сообщение об ошибке. Оно содержит команду, в которой возникла ошибка, указатель и описание ошибки с указанием места в строке, где она произошла.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-211">If the error occurs during script execution or is a parsing error, PowerShell returns a multiline error message that contains the error, a pointer and error message showing where the error is in that line.</span></span> <span data-ttu-id="ec4a2-212">Если терминал не поддерживает цветовые escape-последовательности ANSI (VT100), цвета не отображаются.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-212">If the terminal doesn't support ANSI color escape sequences (VT100), then colors are not displayed.</span></span>

![Отображение ошибки скрипта](./media/What-s-New-in-PowerShell-70/myscript-error.png)

<span data-ttu-id="ec4a2-214">В PowerShell 7 представление **ConciseView** используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-214">The default view in PowerShell 7 is **ConciseView**.</span></span> <span data-ttu-id="ec4a2-215">Ранее представлением по умолчанию было **NormalView**. Пользователь может выбрать его, задав привилегированную переменную `$ErrorView`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-215">The previous default view was **NormalView** and is user selectable by setting the preference variable `$ErrorView`.</span></span>

```powershell
$ErrorView = 'NormalView' # Sets the error view to NormalView
$ErrorView = 'ConciseView' # Sets the error view to ConciseView
```

> [!NOTE]
> <span data-ttu-id="ec4a2-216">В `$Host.PrivateData` добавлено новое свойство **ErrorAccentColor**, позволяющее изменять контрастный цвет сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-216">A new property **ErrorAccentColor** is added to `$Host.PrivateData` to support changing the accent color of the error message.</span></span>

<span data-ttu-id="ec4a2-217">Новый командлет `Get-Error` позволяет получать подробные сведения об ошибке, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-217">A new cmdlet `Get-Error` provides complete detailed view of the fully qualified error when desired.</span></span>
<span data-ttu-id="ec4a2-218">По умолчанию этот командлет выводит полные сведения, включая внутренние исключения, о последней произошедшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-218">By default the cmdlet displays the full details, including inner exceptions, of the last error that occurred.</span></span>

![Выходные данные командлета Get-Error](./media/What-s-New-in-PowerShell-70/myscript-geterror.png)

<span data-ttu-id="ec4a2-220">Командлет `Get-Error` поддерживает входные данные из конвейера посредством встроенной переменной `$Error`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-220">The `Get-Error` cmdlet supports input from the pipeline using the built-in variable `$Error`.</span></span>
<span data-ttu-id="ec4a2-221">`Get-Error` выводит все ошибки из конвейера.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-221">`Get-Error` displays all piped errors.</span></span>

```powershell
$Error | Get-Error
```

<span data-ttu-id="ec4a2-222">Командлет `Get-Error` поддерживает параметр **Newest**, позволяющий указывать, сколько ошибок из текущего сеанса нужно вывести.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-222">The `Get-Error` cmdlet supports the **Newest** parameter, allowing you to specify how many errors from the current session you wish displayed.</span></span>

```powershell
Get-Error -Newest 3 # Displays the lst three errors that occurred in the session
```

<span data-ttu-id="ec4a2-223">См. дополнительные сведения о командлете [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-223">For more information about [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7).</span></span>

## <a name="new-version-notification"></a><span data-ttu-id="ec4a2-224">Уведомление о новой версии</span><span class="sxs-lookup"><span data-stu-id="ec4a2-224">New version notification</span></span>

<span data-ttu-id="ec4a2-225">В PowerShell 7 имеются уведомления об обновлениях, оповещающие пользователей о наличии обновлений для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-225">PowerShell 7 uses update notifications to alert users to the existence of updates to PowerShell.</span></span>
<span data-ttu-id="ec4a2-226">Раз в день PowerShell выполняет запрос к веб-службе, чтобы определить, доступна ли более новая версия.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-226">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-227">Проверка обновлений производится во время первого сеанса в течение 24-часового периода.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-227">The update check happens during the first session in a given 24-hour period.</span></span> <span data-ttu-id="ec4a2-228">По соображениям производительности проверка обновлений инициируется через три секунды после начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-228">For performance reasons, the update check starts 3 seconds after the session begins.</span></span> <span data-ttu-id="ec4a2-229">Уведомление выводится только в начале последующих сеансов.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-229">The notification is shown only on the start of subsequent sessions.</span></span>

<span data-ttu-id="ec4a2-230">По умолчанию PowerShell подписывается на один из двух разных каналов уведомлений в зависимости от версии и ветви.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-230">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="ec4a2-231">В поддерживаемых общедоступных (GA) версиях PowerShell уведомления возвращаются только для обновленных общедоступных выпусков.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-231">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="ec4a2-232">В предварительных выпусках и релизах-кандидатах (RC) выводятся уведомления об обновлениях для предварительных выпусков, релизов-кандидатов и общедоступных выпусков.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-232">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="ec4a2-233">Настроить уведомления об обновлениях можно с помощью переменной среды `$Env:POWERSHELL_UPDATECHECK`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-233">The update notification behavior can be changed using the `$Env:POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="ec4a2-234">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-234">The following values are supported:</span></span>

- <span data-ttu-id="ec4a2-235">**Default** — равносильно не заданной переменной `$Env:POWERSHELL_UPDATECHECK`.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-235">**Default** is the same as not defining `$Env:POWERSHELL_UPDATECHECK`</span></span>
  - <span data-ttu-id="ec4a2-236">В общедоступных выпусках выводятся уведомления об обновлениях для общедоступных выпусков.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-236">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="ec4a2-237">В предварительных выпусках и релизах-кандидатах выводятся уведомления об обновлениях для общедоступных и предварительных выпусков.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-237">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="ec4a2-238">**Off** — отключает функцию уведомлений об обновлениях.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-238">**Off** turns off the update notification feature</span></span>
- <span data-ttu-id="ec4a2-239">**LTS** — выводятся уведомления об обновлениях только для общедоступных выпусков ветви Long Term Servicing Branch (LTS).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-239">**LTS** only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-240">Пока переменная среды `$Env:POWERSHELL_UPDATECHECK` не будет задана впервые, она не существует.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-240">The environment variable `$Env:POWERSHELL_UPDATECHECK` does not exist until it is set for the first time.</span></span>

<span data-ttu-id="ec4a2-241">Настройка уведомлений о версиях только для выпусков `LTS`:</span><span class="sxs-lookup"><span data-stu-id="ec4a2-241">To set the version notification for `LTS` releases only:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'LTS'
```

<span data-ttu-id="ec4a2-242">Настройка уведомлений о версиях по умолчанию (`Default`):</span><span class="sxs-lookup"><span data-stu-id="ec4a2-242">To set the version notification to the `Default` behavior:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'Default'
```

<span data-ttu-id="ec4a2-243">См. дополнительные сведения об [уведомлениях об обновлениях](/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-243">For more information [About Update Notifications](/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7).</span></span>

## <a name="new-dsc-resource-support-with-invoke-dscresource-experimental"></a><span data-ttu-id="ec4a2-244">Поддержка ресурса DSC посредством Invoke-DSCResource (экспериментальная функция)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-244">New DSC Resource support with Invoke-DSCResource (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="ec4a2-245">Это экспериментальная функция под названием **PSDesiredStateConfiguration.InvokeDscResource**.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-245">This is an experimental feature named **PSDesiredStateConfiguration.InvokeDscResource**.</span></span> <span data-ttu-id="ec4a2-246">См. дополнительные сведения об [экспериментальных функциях](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-246">Learn more [About Experimental Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span></span>

<span data-ttu-id="ec4a2-247">Командлет `Invoke-DscResource` выполняет метод указанного ресурса Desired State Configuration (DSC) среды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-247">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="ec4a2-248">Этот командлет вызывает ресурс DSC напрямую, не создавая документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-248">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="ec4a2-249">С его помощью решения для управления конфигурацией могут управлять Windows или Linux посредством ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-249">Using this cmdlet, configuration management products can manage Windows or Linux by using DSC resources.</span></span> <span data-ttu-id="ec4a2-250">Этот командлет также позволяет отлаживать ресурсы, когда модуль DSC работает с включенной отладкой.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-250">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

<span data-ttu-id="ec4a2-251">Эта команда вызывает метод **Set** ресурса с именем Log и задает свойство **Message**.</span><span class="sxs-lookup"><span data-stu-id="ec4a2-251">This command invokes the **Set** method of a resource named Log and specifies a **Message** property.</span></span>

```powershell
Invoke-DscResource -Name Log -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Message = 'Hello World'
}
```

<span data-ttu-id="ec4a2-252">См. дополнительные сведения о командлете [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="ec4a2-252">For more information about [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7).</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="ec4a2-253">Критические изменения и улучшения</span><span class="sxs-lookup"><span data-stu-id="ec4a2-253">Breaking Changes and Improvements</span></span>

### <a name="breaking-changes"></a><span data-ttu-id="ec4a2-254">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="ec4a2-254">Breaking Changes</span></span>

- <span data-ttu-id="ec4a2-255">Поддержка канала LTS и каналов по умолчанию функцией уведомлений об обновлениях (№ 11132)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-255">Make update notification support LTS and default channels (#11132)</span></span>
- <span data-ttu-id="ec4a2-256">Обновление командлета Test-Connection с целью сделать его работу больше похожей на работу аналогичного командлета в Windows PowerShell (№ 10697) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-256">Update Test-Connection to work more like the one in Windows PowerShell (#10697) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-257">Сохранение $?</span><span class="sxs-lookup"><span data-stu-id="ec4a2-257">Preserve $?</span></span> <span data-ttu-id="ec4a2-258">для ParenExpression, SubExpression и ArrayExpression (№ 11040)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-258">for ParenExpression, SubExpression and ArrayExpression (#11040)</span></span>
- <span data-ttu-id="ec4a2-259">Установка текущего каталога в качестве рабочего в Start-Job (№ 10920) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-259">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-260">Согласованное отражение изменений языка и региональных параметров в течение сеанса в $PSCulture (№ 10138) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-260">Make $PSCulture consistently reflect in-session culture changes (#10138) (Thanks @iSazonov!)</span></span>

### <a name="engine-updates-and-fixes"></a><span data-ttu-id="ec4a2-261">Обновления и исправления модулей</span><span class="sxs-lookup"><span data-stu-id="ec4a2-261">Engine Updates and Fixes</span></span>

- <span data-ttu-id="ec4a2-262">Улучшение работы API-интерфейсов точек останова в удаленных сценариях (№ 11312)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-262">Improvements in breakpoint APIs for remote scenarios (#11312)</span></span>
- <span data-ttu-id="ec4a2-263">Устранена утечка определения класса PowerShell в другое пространство выполнения (№ 11273)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-263">Fix PowerShell class definition leaking into another Runspace (#11273)</span></span>
- <span data-ttu-id="ec4a2-264">Устранено ухудшение форматирования из-за добавления примитива FirstOrDefault в выпуске 7.0.0-Preview1 (№ 11258)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-264">Fix a regression in formatting caused by the FirstOrDefault primitive added in 7.0.0-Preview1 (#11258)</span></span>
- <span data-ttu-id="ec4a2-265">Отслеживание дополнительных модулей Майкрософт с помощью телеметрии PowerShell 7 (№ 10751)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-265">Additional Microsoft Modules to track in PS7 Telemetry (#10751)</span></span>
- <span data-ttu-id="ec4a2-266">Вывод одобренных функций из статуса экспериментальных (№ 11303)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-266">Make approved features non-experimental (#11303)</span></span>
- <span data-ttu-id="ec4a2-267">Обновление представления ConciseView для использования TargetObject, если применимо (№ 11075)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-267">Update ConciseView to use TargetObject if applicable (#11075)</span></span>
- <span data-ttu-id="ec4a2-268">Исправлено исключение NullReferenceException в открытых методах CompletionCompleters (№ 11274)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-268">Fix NullReferenceException in CompletionCompleters public methods (#11274)</span></span>
- <span data-ttu-id="ec4a2-269">Исправлена проверка состояния потока контейнера на платформах, отличных от Windows (№ 11301)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-269">Fix apartment thread state check on non-Windows platforms (#11301)</span></span>
- <span data-ttu-id="ec4a2-270">Обновление параметра PSModulePath для сцепления переменных среды процесса и компьютера (№ 11276)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-270">Update setting PSModulePath to concatenate the process and machine environment variables (#11276)</span></span>
- <span data-ttu-id="ec4a2-271">Переход на версию .NET Core 3.1.0 (№ 11260)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-271">Bump .NET Core to 3.1.0 (#11260)</span></span>
- <span data-ttu-id="ec4a2-272">Исправлено обнаружение переменной $PSHOME до переменной $env:PATH (№ 11141)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-272">Fix detection of $PSHOME in front of $env:PATH (#11141)</span></span>
- <span data-ttu-id="ec4a2-273">В pwsh предоставлена возможность наследования переменной $env:PSModulePath для правильного запуска powershell.exe (№ 11057)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-273">Allow pwsh to inherit $env:PSModulePath and enable powershell.exe to start correctly (#11057)</span></span>
- <span data-ttu-id="ec4a2-274">Переход на предварительную версию 1 .NET Core 3.1 (№ 10798)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-274">Move to .NET Core 3.1 preview 1 (#10798)</span></span>
- <span data-ttu-id="ec4a2-275">Рефакторинг проверок тегов повторной обработки в поставщике файловой системы (№ 10431) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-275">Refactor reparse tag checks in file system provider (#10431) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-276">Замена символов CR и новой строки символом 0x23CE в журналах скриптов (№ 10616)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-276">Replace CR and new line with a 0x23CE character in script logging (#10616)</span></span>
- <span data-ttu-id="ec4a2-277">Устранена утечка ресурсов путем отмены регистрации обработчика событий в AppDomain.CurrentDomain.ProcessExit (№ 10626)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-277">Fix a resource leak by unregistering the event handler from AppDomain.CurrentDomain.ProcessExit (#10626)</span></span>
- <span data-ttu-id="ec4a2-278">Добавлена поддержка значения ActionPreference.Break для прерывания работы отладчика при создании сообщения Debug, Error, Information, Progress, Verbose или Warning (№ 8205) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-278">Add support to ActionPreference.Break to break into debugger when Debug, Error, Information, Progress, Verbose or Warning messages are generated (#8205) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-279">Добавлена возможность запуска надстроек панели управления в PowerShell Core без указания расширения .CPL</span><span class="sxs-lookup"><span data-stu-id="ec4a2-279">Enable starting control panel add-ins within PowerShell Core without specifying .CPL extension.</span></span> <span data-ttu-id="ec4a2-280">(№ 9828)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-280">(#9828)</span></span>

### <a name="general-cmdlet-updates-and-fixes"></a><span data-ttu-id="ec4a2-281">Общие обновления и исправления командлетов</span><span class="sxs-lookup"><span data-stu-id="ec4a2-281">General Cmdlet Updates and Fixes</span></span>

- <span data-ttu-id="ec4a2-282">Исправлена проблема в Raspbian, связанная с установкой даты изменения файла в экспериментальной функции UnixStat (№ 11313)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-282">Fix for issue on Raspbian for setting date of file changes in UnixStat Experimental Feature (#11313)</span></span>
- <span data-ttu-id="ec4a2-283">Добавлен параметр -AsPlainText для командлета ConvertFrom-SecureString (№ 11142)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-283">Add -AsPlainText to ConvertFrom-SecureString (#11142)</span></span>
- <span data-ttu-id="ec4a2-284">Добавлена проверка версии WindowsPS для WinCompat (№ 11148)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-284">Added WindowsPS version check for WinCompat (#11148)</span></span>
- <span data-ttu-id="ec4a2-285">Исправлены сообщения об ошибках в некоторых сценариях WinCompat (№ 11259)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-285">Fix error-reporting in some WinCompat scenarios (#11259)</span></span>
- <span data-ttu-id="ec4a2-286">Добавлен собственный двоичный сопоставитель (№ 11032) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-286">Add native binary resolver (#11032) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-287">Изменен способ вычисления ширины символов для учета особенностей символов ККЯ (№ 11262)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-287">Update calculation of char width to respect CJK chars correctly (#11262)</span></span>
- <span data-ttu-id="ec4a2-288">Добавлен командлет Unblock-File для macOS (№ 11137)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-288">Add Unblock-File for macOS (#11137)</span></span>
- <span data-ttu-id="ec4a2-289">Исправлена регрессия в Get-PSCallStack (№ 11210) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-289">Fix regression in Get-PSCallStack (#11210) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-290">Отключена автоматическая загрузка модуля ScheduledJob при использовании командлетов Job (№ 11194)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-290">Remove autoloading of the ScheduledJob module when using Job cmdlets (#11194)</span></span>
- <span data-ttu-id="ec4a2-291">Добавлен аргумент OutputType для командлета Get-Error, и сохраняются исходные имена типов (№ 10856)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-291">Add OutputType to Get-Error cmdlet and preserve original typenames (#10856)</span></span>
- <span data-ttu-id="ec4a2-292">Исправлена проблема с пустой ссылкой в свойстве SupportsVirtualTerminal (№ 11105)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-292">Fix null reference in SupportsVirtualTerminal property (#11105)</span></span>
- <span data-ttu-id="ec4a2-293">Добавлена проверка соблюдения ограничения в командлете Get-WinEvent (№ 10648) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-293">Add limit check in Get-WinEvent (#10648) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-294">Исправление для среды выполнения команд, предотвращающее заполнение параметра -ErrorVariable исключением StopUpstreamCommandsException (№ 10840)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-294">Fix command runtime so StopUpstreamCommandsException doesn't get populated in -ErrorVariable (#10840)</span></span>
- <span data-ttu-id="ec4a2-295">Для собственных команд установлена выходная кодировка [Console]::OutputEncoding (№ 10824)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-295">Set the output encoding to [Console]::OutputEncoding for native commands (#10824)</span></span>
- <span data-ttu-id="ec4a2-296">Поддержка многострочных блоков кода в примерах (№ 10776) (выражаем благодарность @Greg-Smulko)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-296">Support multi-line code blocks in examples (#10776) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="ec4a2-297">Для командлета Select-String добавлен параметр Culture (#10943) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-297">Add Culture parameter to Select-String cmdlet (#10943) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-298">Исправлена проблема, связанная с путем к рабочему каталогу Start-Job с косой чертой в конце (#11041)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-298">Fix Start-Job working directory path with trailing backslash (#11041)</span></span>
- <span data-ttu-id="ec4a2-299">ConvertFrom-Json: распаковка коллекций по умолчанию (№ 10861) (выражаем благодарность @danstur)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-299">ConvertFrom-Json: Unwrap collections by default (#10861) (Thanks @danstur!)</span></span>
- <span data-ttu-id="ec4a2-300">Использование хэш-таблицы с учетом регистра для командлета Group-Object с параметрами -CaseSensitive и -AsHashtable (№ 11030) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-300">Use case-sensitive Hashtable for Group-Object cmdlet with -CaseSensitive and -AsHashtable switches (#11030) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-301">Обработка исключения в случае, если при перестроении пути с целью исправления регистра символов не удается перечислить файлы (№ 11014)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-301">Handle exception if enumerating files fails when rebuilding path to have correct casing (#11014)</span></span>
- <span data-ttu-id="ec4a2-302">Исправление представления ConciseView с целью отображения Activity вместо myCommand (№ 11007)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-302">Fix ConciseView to show Activity instead of myCommand (#11007)</span></span>
- <span data-ttu-id="ec4a2-303">Веб-командлетам разрешено игнорировать состояния ошибки HTTP (№ 10466) (выражаем благодарность @vdamewood)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-303">Allow web cmdlets to ignore HTTP error statuses (#10466) (Thanks @vdamewood!)</span></span>
- <span data-ttu-id="ec4a2-304">Исправлена проблема с передачей нескольких объектов CommandInfo в командлет Get-Command (№ 10929)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-304">Fix piping of more than one CommandInfo to Get-Command (#10929)</span></span>
- <span data-ttu-id="ec4a2-305">Возвращен командлет Get-Counter для Windows (№ 10933)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-305">Add back Get-Counter cmdlet for Windows (#10933)</span></span>
- <span data-ttu-id="ec4a2-306">Командлет ConvertTo-Json теперь рассматривает [AutomationNull]::Value и [NullString]::Value как $null (№ 10957)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-306">Make ConvertTo-Json treat [AutomationNull]::Value and [NullString]::Value as $null (#10957)</span></span>
- <span data-ttu-id="ec4a2-307">Удалены угловые скобки из IPv6-адреса для удаленного взаимодействия через SSH (№ 10968)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-307">Remove brackets from ipv6 address for SSH remoting (#10968)</span></span>
- <span data-ttu-id="ec4a2-308">Устранено аварийное завершение работы в случае, когда команда, отправляемая в pwsh, представляет собой пробел (№ 10977)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-308">Fix crash if command sent to pwsh is just whitespace (#10977)</span></span>
- <span data-ttu-id="ec4a2-309">Добавлены кроссплатформенные командлеты Get-Clipboard и Set-Clipboard (№ 10340)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-309">Added cross-platform Get-Clipboard and Set-Clipboard (#10340)</span></span>
- <span data-ttu-id="ec4a2-310">Исправление, требующее отсутствия дополнительной косой черты при задании исходного пути к объекту файловой системы (№ 10959)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-310">Fix setting original path of filesystem object to not have extra trailing slash (#10959)</span></span>
- <span data-ttu-id="ec4a2-311">Поддержка $null для командлета ConvertTo-Json (№ 10947)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-311">Support $null for ConvertTo-Json (#10947)</span></span>
- <span data-ttu-id="ec4a2-312">Возвращена команда Out-Printer в Windows (№ 10906)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-312">Add back Out-Printer command on Windows (#10906)</span></span>
- <span data-ttu-id="ec4a2-313">Исправлена проблема, связанная с наличием пробела в команде Start-Job -WorkingDirectory (№ 10951)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-313">Fix Start-Job -WorkingDirectory with whitespace (#10951)</span></span>
- <span data-ttu-id="ec4a2-314">При получении значения NULL для параметра в PSConfiguration.cs возвращается значение по умолчанию (№ 10963) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-314">Return default value when getting null for a setting in PSConfiguration.cs (#10963) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-315">Обработка исключения ввода-вывода как устранимого (№ 10950)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-315">Handle IO exception as non-terminating (#10950)</span></span>
- <span data-ttu-id="ec4a2-316">Добавлена сборка GraphicalHost, позволяющая выполнять команды Out-GridView, Show-Command и Get-Help -ShowWindow (№ 10899)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-316">Add GraphicalHost assembly to enable Out-GridView, Show-Command, and Get-Help -ShowWindow (#10899)</span></span>
- <span data-ttu-id="ec4a2-317">Получение ComputerName через конвейер в Get-HotFix (№ 10852) (выражаем благодарность @kvprasoon)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-317">Take ComputerName via pipeline in Get-HotFix (#10852) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="ec4a2-318">Исправлена проблема, связанная с заполнением нажатием клавиши TAB для параметров: теперь общие параметры отображаются как доступные (№ 10850)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-318">Fix tab completion for parameters so that it shows common parameters as available (#10850)</span></span>
- <span data-ttu-id="ec4a2-319">Исправление GetCorrectCasedPath(): перед вызовом First() сначала выполняется проверка того, возвращаются ли какие-либо записи файловой системы (№ 10930)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-319">Fix GetCorrectCasedPath() to first check if any system file entries is returned before calling First() (#10930)</span></span>
- <span data-ttu-id="ec4a2-320">Установка текущего каталога в качестве рабочего в Start-Job (№ 10920) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-320">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-321">Изменение функции TabExpansion2: теперь она не требует параметра -CursorColumn и обрабатывается как $InputScript.Length (№ 10849)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-321">Change TabExpansion2 to not require -CursorColumn and treat as $InputScript.Length (#10849)</span></span>
- <span data-ttu-id="ec4a2-322">Обработка случая, когда узел может не возвращать строки или столбцы экрана (№ 10938)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-322">Handle case where Host may not return Rows or Columns of screen (#10938)</span></span>
- <span data-ttu-id="ec4a2-323">Исправлена проблема, связанная с использованием контрастных цветов для узлов, которые не поддерживают их (№ 10937)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-323">Fix use of accent colors for hosts that don't support them (#10937)</span></span>
- <span data-ttu-id="ec4a2-324">Возвращена команда Update-List (№ 10922)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-324">Add back Update-List command (#10922)</span></span>
- <span data-ttu-id="ec4a2-325">Обновлен идентификатор FWLink для Clear-RecycleBin (№ 10925)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-325">Update FWLink Id for Clear-RecycleBin (#10925)</span></span>
- <span data-ttu-id="ec4a2-326">При заполнении нажатием клавиши TAB файл пропускается, если невозможно прочитать его атрибуты (№ 10910)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-326">During tab completion, skip file if can't read file attributes (#10910)</span></span>
- <span data-ttu-id="ec4a2-327">Возвращен командлет Clear-RecycleBin для Windows (№ 10909)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-327">Add back Clear-RecycleBin for Windows (#10909)</span></span>
- <span data-ttu-id="ec4a2-328">Добавлена переменная `$env:__SuppressAnsiEscapeSequences`, которая определяет, должна ли использоваться escape-последовательность VT в выходных данных (№ 10814)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-328">Add `$env:__SuppressAnsiEscapeSequences` to control whether to have VT escape sequence in output (#10814)</span></span>
- <span data-ttu-id="ec4a2-329">Добавлен параметр -NoEmphasize для раскрашивания выходных данных командлета Select-String (№ 8963) (выражаем благодарность @derek-xia)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-329">Add -NoEmphasize parameter to colorize Select-String output (#8963) (Thanks @derek-xia!)</span></span>
- <span data-ttu-id="ec4a2-330">Возвращен командлет Get-HotFix (№ 10740)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-330">Add back Get-HotFix cmdlet (#10740)</span></span>
- <span data-ttu-id="ec4a2-331">Командлет Add-Type теперь можно использовать в приложениях, в которых размещается PowerShell (№ 10587)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-331">Make Add-Type usable in applications that host PowerShell (#10587)</span></span>
- <span data-ttu-id="ec4a2-332">Более эффективный порядок вычисления в LanguagePrimitives.IsNullLike() (№ 10781) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-332">Use more effective evaluation order in LanguagePrimitives.IsNullLike() (#10781) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-333">Улучшена обработка передаваемых по конвейеру входных данных в виде смешанных коллекций и передаваемых по конвейеру потоков входных данных в Format-Hex (№ 8674) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-333">Improve handling of mixed-collection piped input and piped streams of input in Format-Hex (#8674) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-334">Использование преобразования типов в хэш-таблицах SSHConnection, когда значение имеет непредвиденный тип (№ 10720) (выражаем благодарность @SeeminglyScience)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-334">Use type conversion in SSHConnection hashtables when value doesn't match expected type (#10720) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="ec4a2-335">Исправлено поведение команды Get-Content -ReadCount 0 при задании параметра -TotalCount (№ 10749) (выражаем благодарность @eugenesmlv)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-335">Fix Get-Content -ReadCount 0 behavior when -TotalCount is set (#10749) (Thanks @eugenesmlv!)</span></span>
- <span data-ttu-id="ec4a2-336">Изменен текст сообщения об ошибке отказа в доступе в Get-WinEvent (№ 10639) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-336">Reword access denied error message in Get-WinEvent (#10639) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-337">Поддержка заполнения нажатием клавиши TAB при присвоении значения переменной, являющейся перечислением или переменной с ограничением типа (№ 10646)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-337">Enable tab completion for variable assignment that is enum or type constrained (#10646)</span></span>
- <span data-ttu-id="ec4a2-338">Удалено неиспользуемое свойство удаленного взаимодействия SourceLength, из-за которого возникали проблемы с форматированием (№ 10765)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-338">Remove unused SourceLength remoting property causing formatting issues (#10765)</span></span>
- <span data-ttu-id="ec4a2-339">Для командлета ConvertFrom-StringData добавлен параметр -Delimiter (№ 10665) (выражаем благодарность @steviecoaster)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-339">Add -Delimiter parameter to ConvertFrom-StringData (#10665) (Thanks @steviecoaster!)</span></span>
- <span data-ttu-id="ec4a2-340">Добавлен позиционный параметр для ScriptBlock при использовании командлета Invoke-Command с SSH (№ 10721) (выражаем благодарность @machgo)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-340">Add positional parameter for ScriptBlock when using Invoke-Command with SSH (#10721) (Thanks @machgo!)</span></span>
- <span data-ttu-id="ec4a2-341">Отображение сведений о контексте строки в представлении ConciseView при наличии нескольких строк, но отсутствии имени скрипта (№ 10746)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-341">Show line context information if multiple lines but no script name for ConciseView (#10746)</span></span>
- <span data-ttu-id="ec4a2-342">Добавлена поддержка путей \\wsl$\ к поставщику файловой системы (№ 10674)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-342">Add support for \\wsl$\ paths to file system provider (#10674)</span></span>
- <span data-ttu-id="ec4a2-343">Добавлен отсутствующий текст токена для TokenKind.QuestionMark в средстве синтаксического анализа (№ 10706)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-343">Add the missing token text for TokenKind.QuestionMark in parser (#10706)</span></span>
- <span data-ttu-id="ec4a2-344">В качестве текущего рабочего каталога для каждого выполняющегося скрипта ForEach-Object -Parallel задается расположение вызывающего скрипта</span><span class="sxs-lookup"><span data-stu-id="ec4a2-344">Set current working directory of each ForEach-Object -Parallel running script to the same location as the calling script.</span></span> <span data-ttu-id="ec4a2-345">(№ 10672)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-345">(#10672)</span></span>
- <span data-ttu-id="ec4a2-346">Замена api-ms-win-core-file-l1-2-2.dll на Kernell32.dll для интерфейсов API FindFirstStreamW и FindNextStreamW (№ 10680) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-346">Replace api-ms-win-core-file-l1-2-2.dll with Kernell32.dll for FindFirstStreamW and FindNextStreamW APIs (#10680) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-347">Настройка скрипта форматирования справки для ослабления режима StrictMode (№ 10563)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-347">Tweak help formatting script to be more StrictMode tolerant (#10563)</span></span>
- <span data-ttu-id="ec4a2-348">Для командлета New-Service добавлен параметр -SecurityDescriptorSDDL (№ 10483) (выражаем благодарность @kvprasoon)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-348">Add -SecurityDescriptorSDDL parameter to New-Service (#10483) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="ec4a2-349">Устранены информационные выходные данные, консолидировано использование проверки связи в Test-Connection (№ 10478) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-349">Remove informational output, consolidate ping usage in Test-Connection (#10478) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-350">Чтение специальных точек повторного синтаксического анализа без обращения к ним (№ 10662) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-350">Read special reparse points without accessing them (#10662) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-351">Вывод выходных данных Clear-Host непосредственно в терминал (№ 10681) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-351">Direct Clear-Host output to terminal (#10681) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-352">Возвращен символ новой строки при группировке с помощью Format-Table и -Property (№ 10653)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-352">Add back newline for grouping with Format-Table and -Property (#10653)</span></span>
- <span data-ttu-id="ec4a2-353">Из параметра -InputObject командлета Get-Random удален аргумент [ValidateNotNullOrEmpty], благодаря чему допустима пустая строка (№ 10644)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-353">Remove [ValidateNotNullOrEmpty] from -InputObject on Get-Random to allow empty string (#10644)</span></span>
- <span data-ttu-id="ec4a2-354">Алгоритм определения расстояния между строк при формировании предложений теперь не учитывает регистр символов (№ 10549) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-354">Make suggestion system string distance algorithm case-insensitive (#10549) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-355">Исправлено исключение пустой ссылки при обработке входных данных ForEach-Object -Parallel (№ 10577)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-355">Fix null reference exception in ForEach-Object -Parallel input processing (#10577)</span></span>
- <span data-ttu-id="ec4a2-356">Добавлены определения групповой политики PowerShell Core (№ 10468)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-356">Add PowerShell Core group policy definitions (#10468)</span></span>
- <span data-ttu-id="ec4a2-357">Узел консоли обновлен для поддержки управляющих последовательностей VT XTPUSHSGR и XTPOPSGR, используемых в сценариях компоновки</span><span class="sxs-lookup"><span data-stu-id="ec4a2-357">Update console host to support XTPUSHSGR/XTPOPSGR VT control sequences that are used in composability scenarios.</span></span> <span data-ttu-id="ec4a2-358">(№ 10208)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-358">(#10208)</span></span>
- <span data-ttu-id="ec4a2-359">Для командлета Start-Job добавлен параметр WorkingDirectory (№ 10324) (выражаем благодарность @davinci26)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-359">Add WorkingDirectory parameter to Start-Job (#10324) (Thanks @davinci26!)</span></span>
- <span data-ttu-id="ec4a2-360">Удален обработчик событий, который приводил к ошибочной репликации изменений точек останова в отладчик пространства выполнения узла (№ 10503) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-360">Remove the event handler that was causing breakpoint changes to be erroneously replicated to the host runspace debugger (#10503) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-361">Замена api-ms-win-core-job-12-1-0.dll на Kernell32.dll в интерфейсе API P/Invoke Microsoft.PowerShell.Commands.NativeMethods (№ 10417) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-361">Replace api-ms-win-core-job-12-1-0.dll with Kernell32.dll in Microsoft.PowerShell.Commands.NativeMethods P/Invoke API(#10417) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-362">Исправлены неверные выходные данные для New-Service при присвоении значения переменной и использовании -OutVariable (№ 10444) (выражаем благодарность @kvprasoon)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-362">Fix wrong output for New-Service in variable assignment and -OutVariable (#10444) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="ec4a2-363">Исправлены проблемы в глобальном средстве, связанные с кодом завершения, параметрами командной строки и пробелами в путях (№ 10461)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-363">Fix global tool issues around exit code, command line parameters and path with spaces (#10461)</span></span>
- <span data-ttu-id="ec4a2-364">Исправлена рекурсия в OneDrive — функция FindFirstFileEx() теперь имеет тип SafeFindHandle (№ 10405)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-364">Fix recursion into OneDrive - change FindFirstFileEx() to use SafeFindHandle type (#10405)</span></span>
- <span data-ttu-id="ec4a2-365">Автоматическая загрузка PSReadLine в Windows пропускается, если включено средство чтения с экрана NVDA (№ 10385)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-365">Skip auto-loading PSReadLine on Windows if the NVDA screen reader is active (#10385)</span></span>
- <span data-ttu-id="ec4a2-366">Повышение версии модулей, сборка которых выполнена с помощью PowerShell, до 7.0.0.0 (№ 10356)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-366">Increase built-with-PowerShell module versions to 7.0.0.0 (#10356)</span></span>
- <span data-ttu-id="ec4a2-367">Командлет Add-Type теперь выдает ошибку, если тип с таким именем уже существует (№ 9609) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-367">Add throwing an error in Add-Type if a type with the same name already exists (#9609) (Thanks @iSazonov!)</span></span>

### <a name="performance"></a><span data-ttu-id="ec4a2-368">Производительность</span><span class="sxs-lookup"><span data-stu-id="ec4a2-368">Performance</span></span>

- <span data-ttu-id="ec4a2-369">Не используйте замыкание в Parser.SaveError (№ 11006)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-369">Avoid using closure in Parser.SaveError (#11006)</span></span>
- <span data-ttu-id="ec4a2-370">Улучшено кэширование при создании экземпляров регулярных выражений (№ 10657) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-370">Improve the caching when creating new Regex instances (#10657) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-371">Улучшена обработка данных встроенных типов PowerShell types.ps1xml, typesV3.ps1xml и GetEvent.types.ps1xml (№ 10898)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-371">Improve processing of the PowerShell built-in type data from types.ps1xml, typesV3.ps1xml and GetEvent.types.ps1xml (#10898)</span></span>
- <span data-ttu-id="ec4a2-372">Обновлена функция PSConfiguration.ReadValueFromFile — теперь она работает быстрее и эффективнее использует память (№ 10839)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-372">Update PSConfiguration.ReadValueFromFile to make it faster and more memory efficient (#10839)</span></span>
- <span data-ttu-id="ec4a2-373">Незначительные улучшения производительности при инициализации пространства выполнения (№ 10569) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-373">Add minor performance improvements for runspace initialization (#10569) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-374">Ускорение выполнения командлета ForEach-Object в распространенных сценариях (№ 10454) и исправление проблемы с производительностью ForEach-Object -Parallel при использовании со множеством пространств выполнения (№ 10455)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-374">Make ForEach-Object faster for its commonly used scenarios (#10454) and fix ForEach-Object -Parallel performance problem with many runspaces (#10455)</span></span>

### <a name="code-cleanup"></a><span data-ttu-id="ec4a2-375">Очистка кода</span><span class="sxs-lookup"><span data-stu-id="ec4a2-375">Code Cleanup</span></span>

- <span data-ttu-id="ec4a2-376">Изменение текста комментария и элемента в соответствии со стандартами Майкрософт (№ 11304)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-376">Change comment and element text to meet Microsoft standards (#11304)</span></span>
- <span data-ttu-id="ec4a2-377">Исправление проблем со стилем в файле Compiler.cs (№ 10368) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-377">Cleanup style issues in Compiler.cs (#10368) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-378">Удален неиспользуемый преобразователь типов для CommaDelimitedStringCollection (№ 11000) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-378">Remove the unused type converter for CommaDelimitedStringCollection (#11000) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-379">Исправление проблем со стилем в файле InitialSessionState.cs (№ 10865) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-379">Cleanup style in InitialSessionState.cs (#10865) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-380">Очистка кода в классе PSSession (№ 11001)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-380">Code clean up for PSSession class (#11001)</span></span>
- <span data-ttu-id="ec4a2-381">Удалена неработающая функция "выполнение Update-Help из Get-Help при первом выполнении Get-Help" (№ 10974)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-381">Remove the not-working 'run Update-Help from Get-Help when Get-Help runs for the first time' feature (#10974)</span></span>
- <span data-ttu-id="ec4a2-382">Исправление проблем со стилем (№ 10998) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-382">Fix style issues (#10998) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-383">Очистка: использование псевдонима встроенного типа (№ 10882) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-383">Cleanup: use the built-in type alias (#10882) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-384">Удален неиспользуемый ключ параметра ConsolePrompting; при запросе параметра ExecutionPolicy не создаются лишние строки (№ 10985)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-384">Remove the unused setting key ConsolePrompting and avoid unnecessary string creation when querying ExecutionPolicy setting (#10985)</span></span>
- <span data-ttu-id="ec4a2-385">Отключена проверка уведомлений об обновлениях для ежедневных сборок (№ 10903) (выражаем благодарность @bergmeister)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-385">Disable update notification check for daily builds (#10903) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="ec4a2-386">Восстановлен интерфейс API отладки, который перестал работать из-за исправления № 10338 (№ 10808)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-386">Reinstate debugging API lost in #10338 (#10808)</span></span>
- <span data-ttu-id="ec4a2-387">Удалена ссылка на WorkflowJobSourceAdapter, которая больше не используется (№ 10326) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-387">Remove WorkflowJobSourceAdapter reference that is no longer used (#10326) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-388">Очистка кода списка переходов для интерфейсов COM путем внесения исправлений в атрибуты PreserveSig (№ 9899) (выражаем благодарность @weltkante)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-388">Cleanup COM interfaces in jump list code by fixing PreserveSig attributes (#9899) (Thanks @weltkante!)</span></span>
- <span data-ttu-id="ec4a2-389">Добавлен комментарий, описывающий, почему -ia не является псевдонимом для общего параметра -InformationAction (№ 10703) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-389">Add a comment describing why -ia is not the alias for -InformationAction common parameter (#10703) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-390">Файл InvokeCommandCmdlet.cs переименован в InvokeExpressionCommand.cs (№ 10659) (выражаем благодарность @kilasuit)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-390">Rename InvokeCommandCmdlet.cs to InvokeExpressionCommand.cs (#10659) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="ec4a2-391">Незначительная очистка кода, связанного с уведомлениями об обновлениях (№ 10698)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-391">Add minor code cleanups related to update notifications (#10698)</span></span>
- <span data-ttu-id="ec4a2-392">Удалена нерекомендуемая логика рабочего процесса из скриптов настройки удаленного взаимодействия (№ 10320) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-392">Remove deprecated workflow logic from the remoting setup scripts (#10320) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-393">Обновление формата справки с целью использования правильного регистра символов (№ 10678) (выражаем благодарность @tnieto88)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-393">Update help format to use proper case (#10678) (Thanks @tnieto88!)</span></span>
- <span data-ttu-id="ec4a2-394">Исправление проблем со стилем CodeFactor в фиксациях за последний месяц (№ 10591) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-394">Clean up CodeFactor style issues coming in commits for the last month (#10591) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-395">Исправлена опечатка в описании экспериментальной возможности PSTernaryOperator (№ 10586) (выражаем благодарность @bergmeister)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-395">Fix typo in description of PSTernaryOperator experimental feature (#10586) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="ec4a2-396">Значение перечисления ActionPreference.Suspend переведено в неподдерживаемое зарезервированное состояние; устранено ограничение на использование ActionPreference.Ignore в привилегированных переменных (№ 10317) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-396">Convert ActionPreference.Suspend enumeration value into a non-supported, reserved state, and remove restriction on using ActionPreference.Ignore in preference variables (#10317) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-397">Класс ArrayList заменен на List<T> для повышения удобочитаемости и надежности кода без изменения функциональности (№ 10333) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-397">Replace ArrayList with List<T> to get more readable and reliable code without changing functionality (#10333) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-398">Исправления стиля кода в TestConnectionCommand (№ 10439) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-398">Make code style fixes to TestConnectionCommand (#10439) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-399">Очистка AutomationEngine и удаление лишнего вызова метода SetSessionStateDrive (№ 10416) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-399">Cleanup AutomationEngine and remove extra SetSessionStateDrive method call (#10416) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-400">Переименование атрибута ParameterSetName обратно в Delimiter для командлетов ConvertTo-Csv и ConvertFrom-Csv (№ 10425)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-400">Rename default ParameterSetName back to Delimiter for ConvertTo-Csv and ConvertFrom-Csv (#10425)</span></span>

### <a name="tools"></a><span data-ttu-id="ec4a2-401">Инструменты</span><span class="sxs-lookup"><span data-stu-id="ec4a2-401">Tools</span></span>

- <span data-ttu-id="ec4a2-402">Добавлено значение по умолчанию для свойства SDKToUse для обеспечения сборки в Visual Studio (№ 11085)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-402">Add default setting for the SDKToUse property so that it builds in VS (#11085)</span></span>
- <span data-ttu-id="ec4a2-403">Install-Powershell.ps1: добавлен параметр для использования установки MSI (№ 10921) (выражаем благодарность @MJECloud)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-403">Install-Powershell.ps1: Add parameter to use MSI installation (#10921) (Thanks @MJECloud!)</span></span>
- <span data-ttu-id="ec4a2-404">Добавлены базовые примеры для install-powershell.ps1 (№ 10914) (выражаем благодарность @kilasuit)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-404">Add basic examples for install-powershell.ps1 (#10914) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="ec4a2-405">Install-PowerShellRemoting.ps1 теперь обрабатывает пустую строку в параметре PowerShellHome (№ 10526) (выражаем благодарность @Orca88)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-405">Make Install-PowerShellRemoting.ps1 handle empty string in PowerShellHome parameter (#10526) (Thanks @Orca88!)</span></span>
- <span data-ttu-id="ec4a2-406">Замена /etc/lsb-release на /etc/os-release в install-powershell.sh (№ 10773) (выражаем благодарность @Himura2la)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-406">Switch from /etc/lsb-release to /etc/os-release in install-powershell.sh (#10773) (Thanks @Himura2la!)</span></span>
- <span data-ttu-id="ec4a2-407">Проверка pwsh.exe и pwsh в ежедневной версии в Windows (№ 10738) (выражаем благодарность @centreboard)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-407">Check pwsh.exe and pwsh in daily version on Windows (#10738) (Thanks @centreboard!)</span></span>
- <span data-ttu-id="ec4a2-408">Удален ненужный отвод в installpsh-osx.sh (№ 10752)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-408">Remove unneeded tap in installpsh-osx.sh (#10752)</span></span>
- <span data-ttu-id="ec4a2-409">Обновление файла install-powershell.ps1 для проверки уже установленной ежедневной сборки (№ 10489)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-409">Update install-powershell.ps1 to check for already installed daily build (#10489)</span></span>

### <a name="tests"></a><span data-ttu-id="ec4a2-410">Тесты</span><span class="sxs-lookup"><span data-stu-id="ec4a2-410">Tests</span></span>

- <span data-ttu-id="ec4a2-411">Перевод теста DSC с недостоверным результатом в состояние ожидания (№ 11131)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-411">Make unreliable DSC test pending (#11131)</span></span>
- <span data-ttu-id="ec4a2-412">Исправление теста строковых данных для правильной проверки ключей хэш-таблиц (№ 10810)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-412">Fix stringdata test to correctly validate keys of hashtables (#10810)</span></span>
- <span data-ttu-id="ec4a2-413">Выгрузка тестовых модулей (№ 11061) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-413">Unload test modules (#11061) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-414">Увеличен интервал между повторными попытками проверки URL-адреса (№ 11015)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-414">Increase time between retries of testing URL (#11015)</span></span>
- <span data-ttu-id="ec4a2-415">Уточнено описание тестовых действий</span><span class="sxs-lookup"><span data-stu-id="ec4a2-415">Update tests to accurately describe test actions.</span></span> <span data-ttu-id="ec4a2-416">(№ 10928) (выражаем благодарность @romero126)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-416">(#10928) (Thanks @romero126!)</span></span>
- <span data-ttu-id="ec4a2-417">Ненадежный тест TestAppDomainProcessExitEvenHandlerNotLeaking временно пропускается (№ 10827)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-417">Temporary skip the flaky test TestAppDomainProcessExitEvenHandlerNotLeaking (#10827)</span></span>
- <span data-ttu-id="ec4a2-418">Тест на утечку в обработчике событий теперь выполняется стабильно (№ 10790)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-418">Make the event handler leaking test stable (#10790)</span></span>
- <span data-ttu-id="ec4a2-419">Синхронизация прописных букв в CI YAML (№ 10767) (выражаем благодарность @RDIL)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-419">Sync capitalization in CI YAML (#10767) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="ec4a2-420">Добавлен тест для исправления, связанного с утечкой в обработчике событий (№ 10768)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-420">Add test for the event handler leaking fix (#10768)</span></span>
- <span data-ttu-id="ec4a2-421">Добавлен тест Get-ChildItem (№ 10507) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-421">Add Get-ChildItem test (#10507) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-422">Для устранения неоднозначности в тестах термин "флаг" заменен на "параметр" (№ 10666) (выражаем благодарность @romero126)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-422">Replace ambiguous language for tests from switch to parameter for accuracy (#10666) (Thanks @romero126!)</span></span>
- <span data-ttu-id="ec4a2-423">Добавлена экспериментальная проверка в тесты ForEach-Object -Parallel (№ 10354) (выражаем благодарность @KirkMunro)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-423">Add experimental check to ForEach-Object -Parallel tests (#10354) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="ec4a2-424">Добавлены тесты для проверки Alpine (№ 10428)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-424">Update tests for Alpine validation (#10428)</span></span>

### <a name="build-and-package-improvements"></a><span data-ttu-id="ec4a2-425">Улучшения сборки и упаковки</span><span class="sxs-lookup"><span data-stu-id="ec4a2-425">Build and Package Improvements</span></span>

- <span data-ttu-id="ec4a2-426">Исправлена проблема, связанная с подписанием пакета Nuget при сборке координированного пакета (№ 11316)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-426">Fix Nuget package signing for Coordinated Package build (#11316)</span></span>
- <span data-ttu-id="ec4a2-427">Обновлены зависимости из коллекции PowerShell и NuGet (№ 11323)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-427">Update dependencies from PowerShell Gallery and NuGet (#11323)</span></span>
- <span data-ttu-id="ec4a2-428">Обновление Microsoft.ApplicationInsights с версии 2.11.0 до версии 2.12.0 (№ 11305)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-428">Bump Microsoft.ApplicationInsights from 2.11.0 to 2.12.0 (#11305)</span></span>
- <span data-ttu-id="ec4a2-429">Обновление Microsoft.CodeAnalysis.CSharp с версии 3.3.1 до версии 3.4.0 (№ 11265)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-429">Bump Microsoft.CodeAnalysis.CSharp from 3.3.1 to 3.4.0 (#11265)</span></span>
- <span data-ttu-id="ec4a2-430">Обновлены пакеты для Debian 10 и 11 (№ 11236)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-430">Updates packages for Debian 10 and 11 (#11236)</span></span>
- <span data-ttu-id="ec4a2-431">Включение экспериментальных возможностей только до выпуска RC (№ 11162)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-431">Only enable experimental features prior to RC (#11162)</span></span>
- <span data-ttu-id="ec4a2-432">Изменена минимальная версия macOS (№ 11163)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-432">Update macOS minimum version (#11163)</span></span>
- <span data-ttu-id="ec4a2-433">Обновление NJsonSchema с версии 10.0.27 до версии 10.0.28 (№ 11170)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-433">Bump NJsonSchema from 10.0.27 to 10.0.28 (#11170)</span></span>
- <span data-ttu-id="ec4a2-434">Обновлены ссылки в файлах README.md и metadata.json для Preview.5 (№ 10854)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-434">Updating links in README.md and metadata.json for Preview.5 (#10854)</span></span>
- <span data-ttu-id="ec4a2-435">Выбор файлов для тестов соответствия, относящихся к PowerShell (№ 10837)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-435">Select the files for compliance tests which are owned by PowerShell (#10837)</span></span>
- <span data-ttu-id="ec4a2-436">Реализована возможность сборки пакета MSIX win7x86</span><span class="sxs-lookup"><span data-stu-id="ec4a2-436">Allow win7x86 msix package to build.</span></span> <span data-ttu-id="ec4a2-437">(внутреннее исправление № 10515)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-437">(Internal 10515)</span></span>
- <span data-ttu-id="ec4a2-438">Разрешена передача семантических версий в функцию NormalizeVersion (№ 11087)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-438">Allow semantic versions to be passed to NormalizeVersion function (#11087)</span></span>
- <span data-ttu-id="ec4a2-439">Обновление платформы .NET Core до версии 3.1-preview.3 (№ 11079)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-439">Bump .NET core framework to 3.1-preview.3 (#11079)</span></span>
- <span data-ttu-id="ec4a2-440">Обновление PSReadLine с версии 2.0.0-beta5 до версии 2.0.0-beta6 в /src/Modules (№ 11078)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-440">Bump PSReadLine from 2.0.0-beta5 to 2.0.0-beta6 in /src/Modules (#11078)</span></span>
- <span data-ttu-id="ec4a2-441">Обновление Newtonsoft.Json с версии 12.0.2 до версии 12.0.3 (№ 11037) (№ 11038)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-441">Bump Newtonsoft.Json from 12.0.2 to 12.0.3 (#11037) (#11038)</span></span>
- <span data-ttu-id="ec4a2-442">Добавлены пакеты Debian 10, 11 и CentOS 8 (№ 11028)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-442">Add Debian 10, 11 and CentOS 8 packages (#11028)</span></span>
- <span data-ttu-id="ec4a2-443">Отправка JSON-файла Build-Info с полем ReleaseDate (№ 10986)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-443">Upload Build-Info Json file with the ReleaseDate field (#10986)</span></span>
- <span data-ttu-id="ec4a2-444">Обновление платформы .NET Core до версии 3.1-preview.2 (№ 10993)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-444">Bump .NET core framework to 3.1-preview.2 (#10993)</span></span>
- <span data-ttu-id="ec4a2-445">Реализована возможность сборки пакета MSIX x86 (№ 10934)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-445">Enable build of x86 MSIX package (#10934)</span></span>
- <span data-ttu-id="ec4a2-446">Обновлен URL-адрес скрипта установки пакета SDK dotnet в файле build.psm1 (№ 10927)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-446">Update the dotnet SDK install script URL in build.psm1 (#10927)</span></span>
- <span data-ttu-id="ec4a2-447">Обновление Markdig.Signed с версии 0.17.1 до версии 0.18.0 (№ 10887)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-447">Bump Markdig.Signed from 0.17.1 to 0.18.0 (#10887)</span></span>
- <span data-ttu-id="ec4a2-448">Обновление ThreadJob с версии 2.0.1 до версии 2.0.2 (№ 10886)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-448">Bump ThreadJob from 2.0.1 to 2.0.2 (#10886)</span></span>
- <span data-ttu-id="ec4a2-449">Обновление манифеста AppX и модуля упаковки в соответствии с требованиями Microsoft Store (№ 10878)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-449">Update AppX Manifest and Packaging module to conform to MS Store requirements (#10878)</span></span>
- <span data-ttu-id="ec4a2-450">Обновление ссылки на пакет для SDK PowerShell до версии preview.5 (внутреннее исправление № 10295)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-450">Update package reference for PowerShell SDK to preview.5 (Internal 10295)</span></span>
- <span data-ttu-id="ec4a2-451">Обновление файла ThirdPartyNotices.txt (№ 10834)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-451">Update ThirdPartyNotices.txt (#10834)</span></span>
- <span data-ttu-id="ec4a2-452">Обновление Microsoft.PowerShell.Native до версии 7.0.0-preview.3 (№ 10826)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-452">Bump Microsoft.PowerShell.Native to 7.0.0-preview.3 (#10826)</span></span>
- <span data-ttu-id="ec4a2-453">Обновление Microsoft.ApplicationInsights с версии 2.10.0 до версии 2.11.0 (№ 10608)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-453">Bump Microsoft.ApplicationInsights from 2.10.0 to 2.11.0 (#10608)</span></span>
- <span data-ttu-id="ec4a2-454">Обновление NJsonSchema с версии 10.0.24 до версии 10.0.27 (№10756)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-454">Bump NJsonSchema from 10.0.24 to 10.0.27 (#10756)</span></span>
- <span data-ttu-id="ec4a2-455">Добавление поддержки MacPorts в систему сборки (№ 10736) (выражаем благодарность @Lucius-Q-User)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-455">Add MacPorts support to the build system (#10736) (Thanks @Lucius-Q-User!)</span></span>
- <span data-ttu-id="ec4a2-456">Обновление PackageManagement с версии 1.4.4 до версии 1.4.5 (№ 10728)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-456">Bump PackageManagement from 1.4.4 to 1.4.5 (#10728)</span></span>
- <span data-ttu-id="ec4a2-457">Обновление NJsonSchema с версии 10.0.23 до версии 10.0.24 (№ 10635)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-457">Bump NJsonSchema from 10.0.23 to 10.0.24 (#10635)</span></span>
- <span data-ttu-id="ec4a2-458">Добавление переменной среды для различения телеметрии клиента и сервера в MSI (№ 10612)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-458">Add environment variable to differentiate client/server telemetry in MSI (#10612)</span></span>
- <span data-ttu-id="ec4a2-459">Обновление PSDesiredStateConfiguration с версии 2.0.3 до версии 2.0.4 (№ 10603)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-459">Bump PSDesiredStateConfiguration from 2.0.3 to 2.0.4 (#10603)</span></span>
- <span data-ttu-id="ec4a2-460">Обновление Microsoft.CodeAnalysis.CSharp с версии 3.2.1 до версии 3.3.1 (№ 10607)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-460">Bump Microsoft.CodeAnalysis.CSharp from 3.2.1 to 3.3.1 (#10607)</span></span>
- <span data-ttu-id="ec4a2-461">Обновление до версии .Net Core 3.0 RTM (№ 10604) (выражаем благодарность @bergmeister)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-461">Update to .Net Core 3.0 RTM (#10604) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="ec4a2-462">Обновление версии средства упаковки MSIX в соответствии с требованиями Магазина Windows (№ 10588)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-462">Update MSIX packaging so the version to Windows Store requirements (#10588)</span></span>
- <span data-ttu-id="ec4a2-463">Обновление PowerShellGet с версии 2.2 до версии 2.2.1 (№ 10382)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-463">Bump PowerShellGet version from 2.2 to 2.2.1 (#10382)</span></span>
- <span data-ttu-id="ec4a2-464">Обновление PackageManagement с версии 1.4.3 до версии 1.4.4 (№ 10383)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-464">Bump PackageManagement version from 1.4.3 to 1.4.4 (#10383)</span></span>
- <span data-ttu-id="ec4a2-465">Обновление файлов README.md и metadata.json для версии 7.0.0-preview.4 (внутреннее исправление № 10011)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-465">Update README.md and metadata.json for 7.0.0-preview.4 (Internal 10011)</span></span>
- <span data-ttu-id="ec4a2-466">Обновление версии .Net Core 3.0 с предварительной версии 9 до RC1 (№ 10552) (выражаем благодарность @bergmeister)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-466">Upgrade .Net Core 3.0 version from Preview 9 to RC1 (#10552) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="ec4a2-467">Исправлена проблема, связанная с формированием списка экспериментальных возможностей (внутреннее исправление № 9996)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-467">Fix ExperimentalFeature list generation (Internal 9996)</span></span>
- <span data-ttu-id="ec4a2-468">Обновление PSReadLine с версии 2.0.0-beta4 до версии 2.0.0-beta5 (№ 10536)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-468">Bump PSReadLine version from 2.0.0-beta4 to 2.0.0-beta5 (#10536)</span></span>
- <span data-ttu-id="ec4a2-469">Исправление скрипта сборки выпуска с целью задания тега выпуска</span><span class="sxs-lookup"><span data-stu-id="ec4a2-469">Fix release build script to set release tag</span></span>
- <span data-ttu-id="ec4a2-470">Обновление Microsoft.PowerShell.Native до версии 7.0.0-preview.2 (№ 10519)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-470">Update version of Microsoft.PowerShell.Native to 7.0.0-preview.2 (#10519)</span></span>
- <span data-ttu-id="ec4a2-471">Обновление до версии Netcoreapp3.0 preview9 (№ 10484) (выражаем благодарность @bergmeister)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-471">Upgrade to Netcoreapp3.0 preview9 (#10484) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="ec4a2-472">Ежедневная координированная сборка определяется как ежедневная (№ 10464)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-472">Make sure the daily coordinated build, knows it is a daily build (#10464)</span></span>
- <span data-ttu-id="ec4a2-473">Обновление объединенной сборки пакета для выпуска ежедневных сборок (№ 10449)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-473">Update the combined package build to release the daily builds (#10449)</span></span>
- <span data-ttu-id="ec4a2-474">Удалена ссылка на appveyor (№ 10445) (выражаем благодарность @RDIL)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-474">Remove appveyor reference (#10445) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="ec4a2-475">Обновление NJsonSchema с версии 10.0.22 до версии 10.0.23 (№ 10421)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-475">Bump NJsonSchema version from 10.0.22 to 10.0.23 (#10421)</span></span>
- <span data-ttu-id="ec4a2-476">Отменено удаление папки сборки linux-x64, так как она требуется для некоторых зависимостей для Alpine (№ 10407)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-476">Remove the deletion of linux-x64 build folder because some dependencies for Alpine need it (#10407)</span></span>

### <a name="documentation-and-help-content"></a><span data-ttu-id="ec4a2-477">Документация и содержимое справки</span><span class="sxs-lookup"><span data-stu-id="ec4a2-477">Documentation and Help Content</span></span>

- <span data-ttu-id="ec4a2-478">Рефакторинг журналов изменений в один журнал на каждый выпуск (№ 11165)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-478">Refactor change logs into one log per release (#11165)</span></span>
- <span data-ttu-id="ec4a2-479">Исправлены ссылки перенаправления для справочной документации PowerShell 7 в Интернете (№ 11071)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-479">Fix FWLinks for PowerShell 7 online help documents (#11071)</span></span>
- <span data-ttu-id="ec4a2-480">Обновлен файл CONTRIBUTING.md (№ 11096) (выражаем благодарность @mklement0)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-480">Update CONTRIBUTING.md (#11096) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="ec4a2-481">Исправлены ссылки на документацию по установке в README.md (№ 11083)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-481">Fix installation doc links in README.md (#11083)</span></span>
- <span data-ttu-id="ec4a2-482">Добавлены примеры в скрипт install-powershell.ps1 (№ 11024) (выражаем благодарность @kilasuit)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-482">Adds examples to install-powershell.ps1 script (#11024) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="ec4a2-483">Исправления, касающиеся Select-String emphasis и Import-DscResource, в файле CHANGELOG.md (№ 10890)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-483">Fix to Select-String emphasis and Import-DscResource in CHANGELOG.md (#10890)</span></span>
- <span data-ttu-id="ec4a2-484">Удалена устаревшая ссылка из файла powershell-beginners-guide.md (№ 10926)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-484">Remove the stale link from powershell-beginners-guide.md (#10926)</span></span>
- <span data-ttu-id="ec4a2-485">Объединены стабильные и служебные журналы изменений (№ 10527)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-485">Merge stable and servicing change logs (#10527)</span></span>
- <span data-ttu-id="ec4a2-486">Обновление, касающееся используемой версии .NET, в документации по сборке (№ 10775) (выражаем благодарность @Greg-Smulko)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-486">Update used .NET version in build docs (#10775) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="ec4a2-487">Ссылки на MSDN заменены на ссылки на docs.microsoft.com в powershell-beginners-guide.md (№ 10778) (выражаем благодарность @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-487">Replace links from MSDN to docs.microsoft.com in powershell-beginners-guide.md (#10778) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="ec4a2-488">Исправлена неработающая ссылка на обзор DSC (№ 10702)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-488">Fix broken DSC overview link (#10702)</span></span>
- <span data-ttu-id="ec4a2-489">В Support_Question.md добавлена ссылка на Stack Overflow как на еще один ресурс сообщества (№ 10638) (выражаем благодарность @mklement0)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-489">Update Support_Question.md to link to Stack Overflow as another community resource (#10638) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="ec4a2-490">В шаблон запроса распространения добавлена архитектура процессора (№ 10661)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-490">Add processor architecture to distribution request template (#10661)</span></span>
- <span data-ttu-id="ec4a2-491">В обучающую документацию PowerShell добавлена новая книга о PowerShell MoL (№ 10602)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-491">Add new PowerShell MoL book to learning PowerShell docs (#10602)</span></span>
- <span data-ttu-id="ec4a2-492">Обновлен файл README.md и метаданные для выпусков v6.1.6 и v6.2.3 (№ 10523)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-492">Update README.md and metadata for v6.1.6 and v6.2.3 releases (#10523)</span></span>
- <span data-ttu-id="ec4a2-493">Исправлена опечатка в файле README.md (№ 10465) (выражаем благодарность @vedhasp)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-493">Fix a typo in README.md (#10465) (Thanks @vedhasp!)</span></span>
- <span data-ttu-id="ec4a2-494">В обучающие ресурсы добавлена ссылка на модуль PSKoans (№ 10369) (выражаем благодарность @vexx32)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-494">Add a reference to PSKoans module to Learning Resources documentation (#10369) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="ec4a2-495">Обновление файлов README.md и metadata.json для версии 7.0.0-preview.3 (№ 10393)</span><span class="sxs-lookup"><span data-stu-id="ec4a2-495">Update README.md and metadata.json for 7.0.0-preview.3 (#10393)</span></span>
