---
title: Разрешение конфликтов зависимостей сборок для модулей PowerShell
description: При написании двоичного модуля PowerShell в C# можно использовать зависимости от других пакетов или библиотек для дополнительных функциональных возможностей.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 536bcfd1ced536faccde0d6c5bc483cdaf31ce68
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87775191"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a><span data-ttu-id="19fb6-103">Разрешение конфликтов зависимостей сборок для модулей PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fb6-103">Resolving PowerShell module assembly dependency conflicts</span></span>

<span data-ttu-id="19fb6-104">При написании двоичного модуля PowerShell в C# можно использовать зависимости от других пакетов или библиотек для дополнительных функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-104">When writing a binary PowerShell module in C#, it's natural to take dependencies on other packages or libraries to provide functionality.</span></span> <span data-ttu-id="19fb6-105">Зависимости от других библиотек помогают повторно использовать код.</span><span class="sxs-lookup"><span data-stu-id="19fb6-105">Taking dependencies on other libraries is desirable for code reuse.</span></span> <span data-ttu-id="19fb6-106">PowerShell всегда загружает сборки в один и тот же контекст.</span><span class="sxs-lookup"><span data-stu-id="19fb6-106">PowerShell always loads assemblies into the same context.</span></span> <span data-ttu-id="19fb6-107">В результате зависимости модуля могут конфликтовать с уже загруженными библиотеками DLL и вы не сможете использовать два несвязанных модуля в одном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-107">This presents issues when a module's dependencies conflict with already-loaded DLLs and may prevent using two otherwise unrelated modules in the same PowerShell session.</span></span>

<span data-ttu-id="19fb6-108">Если у вас возникла эта проблема, отображается сообщение об ошибке следующего вида.</span><span class="sxs-lookup"><span data-stu-id="19fb6-108">If you've had this problem, you've seen an error message like this:</span></span>

![Сообщение об ошибке конфликта при загрузке сборки](./media/resolving-dependency-conflicts/moduleconflict.png)

<span data-ttu-id="19fb6-110">В этой статье рассматривается, как возникают конфликты зависимостей в PowerShell и как можно их устранить.</span><span class="sxs-lookup"><span data-stu-id="19fb6-110">This article looks at some of the ways dependency conflicts occur in PowerShell and ways to mitigate dependency conflict issues.</span></span> <span data-ttu-id="19fb6-111">Даже если вы не являетесь автором модуля, вы можете принять меры, чтобы решить проблему конфликта зависимостей в модулях, которые вы используете.</span><span class="sxs-lookup"><span data-stu-id="19fb6-111">Even if you're not a module author, there are some tricks in here that might help you with dependency conflicts occurring in modules that you use.</span></span>

## <a name="why-do-dependency-conflicts-occur"></a><span data-ttu-id="19fb6-112">Почему возникают конфликты зависимостей?</span><span class="sxs-lookup"><span data-stu-id="19fb6-112">Why do dependency conflicts occur?</span></span>

<span data-ttu-id="19fb6-113">В .NET конфликты зависимостей возникают, когда две версии одной сборки загружаются в один и тот же _контекст загрузки сборок_.</span><span class="sxs-lookup"><span data-stu-id="19fb6-113">In .NET, dependency conflicts occur when two versions of the same assembly are loaded into the same _Assembly Load Context_.</span></span> <span data-ttu-id="19fb6-114">Точное значение этого термина зависит от платформы .NET, и об этом мы поговорим [позже](#powershell-and-net).</span><span class="sxs-lookup"><span data-stu-id="19fb6-114">This term means slightly different things on different .NET platforms, which is covered [later](#powershell-and-net).</span></span> <span data-ttu-id="19fb6-115">Этот конфликт часто возникает в программном обеспечении, где используются зависимости с версиями.</span><span class="sxs-lookup"><span data-stu-id="19fb6-115">This conflict is a common problem that occurs in any software where versioned dependencies are used.</span></span> <span data-ttu-id="19fb6-116">Поскольку простых решений не существует и многие платформы разрешения зависимостей пытаются решить проблему разными способами, такая ситуация часто называется dependency hell, то есть "ад зависимостей".</span><span class="sxs-lookup"><span data-stu-id="19fb6-116">Because there are no simple solutions, and because many dependency-resolution frameworks try to solve the problem in different ways, this situation is often called "dependency hell".</span></span>

<span data-ttu-id="19fb6-117">Проблемы, связанные с конфликтами, осложняются тем фактом, что проект почти никогда намеренно или напрямую не зависит от двух версий одной и той же зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-117">Conflict issues are compounded by the fact that a project almost never deliberately or directly depends on two versions of the same dependency.</span></span> <span data-ttu-id="19fb6-118">Вместо этого проект имеет две зависимости или более, для каждой из которых требуется своя версия одной зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-118">Instead, the project has two or more dependencies that each require a different version of the same dependency.</span></span>

<span data-ttu-id="19fb6-119">Предположим, что приложение .NET, `DuckBuilder`, включает в себя две зависимости для разных функций и выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-119">For example, say your .NET application, `DuckBuilder`, brings in two dependencies, to perform parts of its functionality and looks like this:</span></span>

![Две зависимости от DuckBuilder требуют разных версий Newtonsoft.Json](./media/resolving-dependency-conflicts/dep-conflict.jpg)

<span data-ttu-id="19fb6-121">Так как `Contoso.ZipTools` и `Fabrikam.FileHelpers` зависят от разных версий `Newtonsoft.Json`, может возникнуть конфликт зависимостей исходя из способа загрузки каждой зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-121">Because `Contoso.ZipTools` and `Fabrikam.FileHelpers` both depend on different versions of `Newtonsoft.Json`, there may be a dependency conflict depending on how each dependency is loaded.</span></span>

### <a name="conflicting-with-powershells-dependencies"></a><span data-ttu-id="19fb6-122">Конфликт с зависимостями PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fb6-122">Conflicting with PowerShell's dependencies</span></span>

<span data-ttu-id="19fb6-123">В PowerShell проблема с конфликтом зависимостей усугубляется, так как модули PowerShell и собственные зависимости PowerShell загружаются в один и тот же общий контекст.</span><span class="sxs-lookup"><span data-stu-id="19fb6-123">In PowerShell, the dependency conflict issue is magnified because PowerShell modules and PowerShell's own dependencies are loaded into the same shared context.</span></span> <span data-ttu-id="19fb6-124">Это означает, что обработчик PowerShell и все загруженные модули PowerShell не должны иметь конфликтующих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-124">This means the PowerShell engine and all loaded PowerShell modules must not have conflicting dependencies.</span></span> <span data-ttu-id="19fb6-125">Классический пример — `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-125">A classic example of this is `Newtonsoft.Json`:</span></span>

![Модуль FictionalTools зависит от более новой версии Newtonsoft.Json, чем PowerShell](./media/resolving-dependency-conflicts/engine-conflict.jpg)

<span data-ttu-id="19fb6-127">В этом примере модуль `FictionalTools` зависит от версии `Newtonsoft.Json` `12.0.3`, которая является более новой версией `Newtonsoft.Json`, чем `11.0.2` в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-127">In this example, the module `FictionalTools` depends on `Newtonsoft.Json` version `12.0.3`, which is a newer version of `Newtonsoft.Json` than `11.0.2` that ships in the example PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="19fb6-128">Это просто пример; сейчас PowerShell 7 поставляется с `Newtonsoft.Json 12.0.3`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-128">This is an example and PowerShell 7 currently ships with `Newtonsoft.Json 12.0.3`.</span></span>

<span data-ttu-id="19fb6-129">Поскольку модуль зависит от более новой версии сборки, он не принимает версию, которая уже загружена в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-129">Because the module depends on a newer version of the assembly, it won't accept the version that PowerShell already has loaded.</span></span> <span data-ttu-id="19fb6-130">Но раз PowerShell уже загрузил версию сборки, модуль не может загрузить собственную версию с помощью стандартного механизма загрузки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-130">But because PowerShell has already loaded a version of the assembly, the module can't load its own version using the conventional load mechanism.</span></span>

### <a name="conflicting-with-another-modules-dependencies"></a><span data-ttu-id="19fb6-131">Конфликт с зависимостями другого модуля</span><span class="sxs-lookup"><span data-stu-id="19fb6-131">Conflicting with another module's dependencies</span></span>

<span data-ttu-id="19fb6-132">Еще один распространенный сценарий в PowerShell — загрузка двух модулей, которые зависят от разных версий одной сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-132">Another common scenario in PowerShell is that a module is loaded that depends on one version of an assembly, and then another module is loaded later that depends on a different version of that assembly.</span></span>

<span data-ttu-id="19fb6-133">Часто это выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-133">This often looks like the following:</span></span>

![Для двух модулей PowerShell требуются разные версии зависимости Microsoft.Extensions.Logging](./media/resolving-dependency-conflicts/mod-conflict.jpg)

<span data-ttu-id="19fb6-135">В этом случае для модуля `FictionalTools` требуется более новая версия `Microsoft.Extensions.Logging`, чем для модуля `FilesystemManager`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-135">In this case, the `FictionalTools` module requires a newer version of `Microsoft.Extensions.Logging` than the `FilesystemManager` module.</span></span>

<span data-ttu-id="19fb6-136">Представьте, что эти модули загружают свои зависимости, помещая сборки зависимостей в тот же каталог, где находится сборка корневого модуля.</span><span class="sxs-lookup"><span data-stu-id="19fb6-136">Imagine these modules load their dependencies by placing the dependency assemblies in the same directory as the root module assembly.</span></span> <span data-ttu-id="19fb6-137">Это позволяет платформе .NET неявно загружать их по имени.</span><span class="sxs-lookup"><span data-stu-id="19fb6-137">This allows .NET to implicitly load them by name.</span></span> <span data-ttu-id="19fb6-138">Если вы используете PowerShell 7 (на платформе .NET Core 3.1), можно загрузить и запустить `FictionalTools`, а затем загрузить и запустить `FilesystemManager` без проблем.</span><span class="sxs-lookup"><span data-stu-id="19fb6-138">If we're running PowerShell 7 (on top of .NET Core 3.1), we can load and run `FictionalTools`, then load and run `FilesystemManager` without issue.</span></span> <span data-ttu-id="19fb6-139">Однако в новом сеансе, если мы загружаем и запускаем `FilesystemManager`, а затем загружаем `FictionalTools`, мы получаем `FileLoadException` из команды `FictionalTools`, так как для нее требуется более новая версия `Microsoft.Extensions.Logging`, чем загруженная.</span><span class="sxs-lookup"><span data-stu-id="19fb6-139">However, in a new session, if we load and run `FilesystemManager`, then load `FictionalTools`, we get a `FileLoadException` from the `FictionalTools` command because it requires a newer version of `Microsoft.Extensions.Logging` than the one loaded.</span></span>
<span data-ttu-id="19fb6-140">`FictionalTools` не удается загрузить требуемую версию, так как сборка с таким именем уже загружена.</span><span class="sxs-lookup"><span data-stu-id="19fb6-140">`FictionalTools` can't load the version needed because an assembly of the same name has already been loaded.</span></span>

## <a name="powershell-and-net"></a><span data-ttu-id="19fb6-141">PowerShell и .NET</span><span class="sxs-lookup"><span data-stu-id="19fb6-141">PowerShell and .NET</span></span>

<span data-ttu-id="19fb6-142">PowerShell выполняется на платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-142">PowerShell runs on the .NET platform.</span></span> <span data-ttu-id="19fb6-143">.NET отвечает за разрешение и загрузку зависимостей сборок, поэтому мы должны понимать, как работает .NET, чтобы разбираться в конфликтах зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-143">NET is ultimately responsible for resolving and loading assembly dependencies, so we must understand how .NET operates here to understand dependency conflicts.</span></span>

<span data-ttu-id="19fb6-144">Кроме того, мы должны принять тот факт, что разные версии PowerShell работают в различных реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-144">We must also confront the fact that different versions of PowerShell run on different .NET implementations.</span></span> <span data-ttu-id="19fb6-145">Как правило, PowerShell 5.1 и более ранних версий работает на .NET Framework, а PowerShell 6 и более поздних версий — на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="19fb6-145">In general, PowerShell 5.1 and below run on .NET Framework, while PowerShell 6 and above run on .NET Core.</span></span> <span data-ttu-id="19fb6-146">Эти две реализации .NET загружают и обрабатывают сборки по-разному.</span><span class="sxs-lookup"><span data-stu-id="19fb6-146">These two implementations of .NET load and handle assemblies differently.</span></span>
<span data-ttu-id="19fb6-147">Это означает, что конфликты зависимостей по-разному разрешаются на разных платформах .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-147">This means that resolving dependency conflicts can vary depending on the underlying .NET platform.</span></span>

### <a name="assembly-load-contexts"></a><span data-ttu-id="19fb6-148">Контексты загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-148">Assembly Load Contexts</span></span>

<span data-ttu-id="19fb6-149">В .NET _контекст загрузки сборок_ (ALC) — это пространство имен среды выполнения, в которое загружаются сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-149">In .NET, an _Assembly Load Context_ (ALC) that is a runtime namespace into which assemblies are loaded.</span></span> <span data-ttu-id="19fb6-150">Имена сборок должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="19fb6-150">The assemblies' names must be unique.</span></span> <span data-ttu-id="19fb6-151">Эта концепция позволяет уникально разрешать сборки по имени в каждом контексте загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-151">This concept allows assemblies to be uniquely resolved by name in each ALC.</span></span>

### <a name="assembly-reference-loading-in-net"></a><span data-ttu-id="19fb6-152">Загрузка ссылок на сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="19fb6-152">Assembly reference loading in .NET</span></span>

<span data-ttu-id="19fb6-153">Семантика загрузки сборок зависит как от реализации .NET (.NET Core или .NET Framework), так и от .NET API, используемого для загрузки определенной сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-153">The semantics of assembly loading depend on both the .NET implementation (.NET Core vs .NET Framework) and the .NET API used to load a particular assembly.</span></span> <span data-ttu-id="19fb6-154">Мы не будем останавливаться на этом, но в разделе [Дополнительные ресурсы](#further-reading) приводятся ссылки на статьи о том, как работает загрузка сборок .NET в каждой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-154">Rather than go into detail here, there are links in the [Further reading](#further-reading) section that go into great detail on how .NET assembly loading works in each .NET implementation.</span></span>

<span data-ttu-id="19fb6-155">В этой статье мы будем упоминать следующие механизмы.</span><span class="sxs-lookup"><span data-stu-id="19fb6-155">In this article we'll refer to the following mechanisms:</span></span>

- <span data-ttu-id="19fb6-156">Неявная загрузка сборки (`Assembly.Load(AssemblyName)`), когда .NET неявно пытается загрузить сборку по имени из ссылки на статическую сборку в коде .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-156">Implicit assembly loading (effectively `Assembly.Load(AssemblyName)`), when .NET implicitly tries to load an assembly by name from a static assembly reference in .NET code.</span></span>
- <span data-ttu-id="19fb6-157">`Assembly.LoadFrom()`, ориентированный на подключаемый модуль API загрузки, который добавляет обработчики для разрешения зависимостей загруженной библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="19fb6-157">`Assembly.LoadFrom()`, a plugin-oriented loading API that adds handlers to resolve dependencies of the loaded DLL.</span></span> <span data-ttu-id="19fb6-158">Этот метод может не разрешать зависимости нужным образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-158">This method may not resolve dependencies the way we want.</span></span>
- <span data-ttu-id="19fb6-159">`Assembly.LoadFile()`, базовый API загрузки, предназначенный для загрузки только запрошенной сборки и не обрабатывающий зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-159">`Assembly.LoadFile()`, a basic loading API intended to load only the assembly asked for and does not handle any dependencies.</span></span>

### <a name="differences-in-net-framework-vs-net-core"></a><span data-ttu-id="19fb6-160">Различия между .NET Framework и .NET Core</span><span class="sxs-lookup"><span data-stu-id="19fb6-160">Differences in .NET Framework vs .NET Core</span></span>

<span data-ttu-id="19fb6-161">Способ работы этих API немного различается в .NET Core и .NET Framework, поэтому изучите материалы по [ссылкам](#further-reading).</span><span class="sxs-lookup"><span data-stu-id="19fb6-161">The way these APIs work has changed in subtle ways between .NET Core and .NET Framework, so it's worth reading through the included [links](#further-reading).</span></span> <span data-ttu-id="19fb6-162">Важно отметить, что контексты загрузки сборок и другие механизмы разрешения сборок различаются в .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="19fb6-162">Importantly, Assembly Load Contexts and other assembly resolution mechanisms have changed between .NET Framework and .NET Core.</span></span>

<span data-ttu-id="19fb6-163">В частности, .NET Framework имеет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="19fb6-163">In particular, .NET Framework has the following features:</span></span>

- <span data-ttu-id="19fb6-164">Глобальный кэш сборок для разрешения сборок на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="19fb6-164">The Global Assembly Cache, for machine-wide assembly resolution</span></span>
- <span data-ttu-id="19fb6-165">Домены приложений, которые работают как внутрипроцессные песочницы для изоляции сборок, также представляют уровень сериализации, который следует учитывать.</span><span class="sxs-lookup"><span data-stu-id="19fb6-165">Application Domains, which work like in-process sandboxes for assembly isolation, but also present a serialization layer to contend with</span></span>
- <span data-ttu-id="19fb6-166">Ограниченная модель контекста загрузки сборок, подробно описанная [здесь](/dotnet/framework/deployment/best-practices-for-assembly-loading), имеет фиксированный набор контекстов загрузки сборок, каждый из которых имеет собственное поведение:</span><span class="sxs-lookup"><span data-stu-id="19fb6-166">A limited assembly load context model, explained in depth [here](/dotnet/framework/deployment/best-practices-for-assembly-loading), that has a fixed set of assembly load contexts, each with their own behavior:</span></span>
  - <span data-ttu-id="19fb6-167">контекст загрузки по умолчанию, где сборки загружаются по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="19fb6-167">The default load context, where assemblies are loaded by default</span></span>
  - <span data-ttu-id="19fb6-168">контекст, из которого выполняется загрузка, для загрузки сборок вручную во время выполнения;</span><span class="sxs-lookup"><span data-stu-id="19fb6-168">The load-from context, for loading assemblies manually at runtime</span></span>
  - <span data-ttu-id="19fb6-169">контекст только для отражения, предназначенный для безопасной загрузки сборок для чтения их метаданных без запуска;</span><span class="sxs-lookup"><span data-stu-id="19fb6-169">The reflection-only context, for safely loading assemblies to read their metadata without running them</span></span>
  - <span data-ttu-id="19fb6-170">загадочное пространство, где находятся сборки, загруженные с помощью `Assembly.LoadFile(string path)` и `Assembly.Load(byte[] asmBytes)`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-170">The mysterious void that assemblies loaded with `Assembly.LoadFile(string path)` and `Assembly.Load(byte[] asmBytes)` live in</span></span>

<span data-ttu-id="19fb6-171">В .NET Core (и .NET 5+) эти сложности заменены на упрощенную модель.</span><span class="sxs-lookup"><span data-stu-id="19fb6-171">.NET Core (and .NET 5+) has replaced this complexity with a simpler model:</span></span>

- <span data-ttu-id="19fb6-172">Глобальный кэш сборок отсутствует.</span><span class="sxs-lookup"><span data-stu-id="19fb6-172">No Global Assembly Cache.</span></span> <span data-ttu-id="19fb6-173">Приложения содержат все собственные зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-173">Applications bring all their own dependencies.</span></span> <span data-ttu-id="19fb6-174">Это позволяет исключить внешний фактор для разрешения зависимостей в приложениях, благодаря чему разрешение зависимостей проще воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="19fb6-174">This removes an external factor for dependency resolution in applications, making dependency resolution more reproducible.</span></span>
  <span data-ttu-id="19fb6-175">PowerShell как узел подключаемого модуля немного усложняет этот процесс для модулей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-175">PowerShell, as the plugin host, complicates this slightly for modules.</span></span> <span data-ttu-id="19fb6-176">Его зависимости в `$PSHOME` являются общими для всех модулей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-176">Its dependencies in `$PSHOME` are shared with all modules.</span></span>
- <span data-ttu-id="19fb6-177">Только один домен приложения без возможности создавать новые.</span><span class="sxs-lookup"><span data-stu-id="19fb6-177">Only one Application Domain, and no ability to create new ones.</span></span> <span data-ttu-id="19fb6-178">Понятие предметной области приложения поддерживается в .NET Core исключительно для глобального состояния процесса .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-178">The Application Domain concept is maintained in .NET Core purely to be the global state of the .NET process.</span></span>
- <span data-ttu-id="19fb6-179">Новая расширяемая модель контекста загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-179">A new, extensible Assembly Load Context model.</span></span> <span data-ttu-id="19fb6-180">Для разрешения сборок можно использовать пространство имен, поместив его в новый контекст загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-180">Assembly resolution can be namespaced by putting it in a new ALC.</span></span> <span data-ttu-id="19fb6-181">Процессы .NET Core начинаются с одного контекста загрузки сборок по умолчанию, в который загружаются все сборки</span><span class="sxs-lookup"><span data-stu-id="19fb6-181">.NET Core processes begin with a single default ALC into which all assemblies are loaded.</span></span> <span data-ttu-id="19fb6-182">(за исключением тех, которые были загружены с `Assembly.LoadFile(string)` и `Assembly.Load(byte[])`). Но процесс может создавать и определять собственные пользовательские контексты загрузки сборок с собственной логикой загрузки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-182">(except for those loaded with `Assembly.LoadFile(string)` and `Assembly.Load(byte[])`) But the process can create and define its own custom ALCs with its own loading logic.</span></span> <span data-ttu-id="19fb6-183">При загрузке сборки первый контекст загрузки сборки, в который она загружается, отвечает за разрешение зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-183">When an assembly is loaded, the first ALC it is loaded into is responsible for resolving its dependencies.</span></span> <span data-ttu-id="19fb6-184">Это создает возможности для реализации мощных механизмов загрузки подключаемого модуля .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-184">This creates opportunities to implement powerful .NET plugin loading mechanisms.</span></span>

<span data-ttu-id="19fb6-185">В обеих реализациях сборки загружаются неактивно.</span><span class="sxs-lookup"><span data-stu-id="19fb6-185">In both implementations, assemblies are loaded lazily.</span></span> <span data-ttu-id="19fb6-186">То есть они загружаются, когда метод, запрашивающий их тип, выполняется в первый раз.</span><span class="sxs-lookup"><span data-stu-id="19fb6-186">This means that they are loaded when a method requiring their type is run for the first time.</span></span>

<span data-ttu-id="19fb6-187">Например, ниже приведены две версии одного и того же кода, которые загружают зависимость в разное время.</span><span class="sxs-lookup"><span data-stu-id="19fb6-187">For example, here are two versions of the same code that load a dependency at different times.</span></span>

<span data-ttu-id="19fb6-188">Первый всегда загружает свою зависимость при вызове `Program.GetRange()`, так как ссылка на зависимость лексически представлена в методе:</span><span class="sxs-lookup"><span data-stu-id="19fb6-188">The first always loads its dependency when `Program.GetRange()` is called, because the dependency reference is lexically present within the method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

<span data-ttu-id="19fb6-189">Вторая загружает зависимость только в том случае, если параметр `limit` имеет значение 20 или более, из-за внутреннего косвенного обращения через метод:</span><span class="sxs-lookup"><span data-stu-id="19fb6-189">The second will load its dependency only if the `limit` parameter is 20 or more, because of the internal indirection through a method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

<span data-ttu-id="19fb6-190">Это хороший подход, поскольку он сводит к минимуму операции ввода-вывода в памяти и файловой системе и более эффективно использует ресурсы.</span><span class="sxs-lookup"><span data-stu-id="19fb6-190">This is a good practice since it minimizes the memory and filesystem I/O and uses the resources more efficiently.</span></span> <span data-ttu-id="19fb6-191">Но есть и побочный эффект — мы не узнаем о сбое загрузки сборки, пока не достигнем пути к коду, пытающегося загрузить сборку.</span><span class="sxs-lookup"><span data-stu-id="19fb6-191">The unfortunate a side effect of this is that we won't know that the assembly fails to load until we reach the code path that tries to load the assembly.</span></span>

<span data-ttu-id="19fb6-192">Кроме того, при таком подходе возникают временные условия для конфликтов при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-192">It can also create a timing condition for assembly load conflicts.</span></span> <span data-ttu-id="19fb6-193">Если две части одной и той же программы пытаются загрузить разные версии одной и той же сборки, то загружаемая версия зависит от того, какой путь к коду выполняется первым.</span><span class="sxs-lookup"><span data-stu-id="19fb6-193">If two parts of the same program try to load different versions of the same assembly, the version loaded depends on which code path is run first.</span></span>

<span data-ttu-id="19fb6-194">Для PowerShell это означает, что следующие факторы могут повлиять на конфликт загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-194">For PowerShell, this means that the following factors can affect an assembly load conflict:</span></span>

- <span data-ttu-id="19fb6-195">Какой модуль загружен первым?</span><span class="sxs-lookup"><span data-stu-id="19fb6-195">Which module was loaded first?</span></span>
- <span data-ttu-id="19fb6-196">Выполнялся ли путь к коду, использующий библиотеку зависимостей?</span><span class="sxs-lookup"><span data-stu-id="19fb6-196">Was the code path that uses the dependency library run?</span></span>
- <span data-ttu-id="19fb6-197">Загружает ли PowerShell конфликтующую зависимость при запуске или только по определенным путям к коду?</span><span class="sxs-lookup"><span data-stu-id="19fb6-197">Does PowerShell load a conflicting dependency at startup or only under certain code paths?</span></span>

## <a name="quick-fixes-and-their-limitations"></a><span data-ttu-id="19fb6-198">Быстрые исправления и их ограничения</span><span class="sxs-lookup"><span data-stu-id="19fb6-198">Quick fixes and their limitations</span></span>

<span data-ttu-id="19fb6-199">В некоторых случаях можно внести небольшие изменения в модуль и исправить проблему с минимальными усилиями.</span><span class="sxs-lookup"><span data-stu-id="19fb6-199">In some cases, it's possible to make small adjustments to your module and fix things with minimal effort.</span></span> <span data-ttu-id="19fb6-200">Но эти решения обычно имеют свои особенности.</span><span class="sxs-lookup"><span data-stu-id="19fb6-200">But these solutions tend to come with caveats.</span></span> <span data-ttu-id="19fb6-201">Они могут применяться к конкретному модулю, но не являются универсальными.</span><span class="sxs-lookup"><span data-stu-id="19fb6-201">While they may apply to your module, they won't work for every module.</span></span>

### <a name="change-your-dependency-version"></a><span data-ttu-id="19fb6-202">Изменение версии зависимости</span><span class="sxs-lookup"><span data-stu-id="19fb6-202">Change your dependency version</span></span>

<span data-ttu-id="19fb6-203">Самый простой способ избежать конфликтов зависимостей — согласовать зависимость.</span><span class="sxs-lookup"><span data-stu-id="19fb6-203">The simplest way to avoid dependency conflicts is to agree on a dependency.</span></span> <span data-ttu-id="19fb6-204">Это можно сделать в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="19fb6-204">This may be possible when:</span></span>

- <span data-ttu-id="19fb6-205">У вас возник конфликт с прямой зависимостью модуля, и вы управляете версией.</span><span class="sxs-lookup"><span data-stu-id="19fb6-205">Your conflict is with a direct dependency of your module and you control the version.</span></span>
- <span data-ttu-id="19fb6-206">Конфликт связан с косвенной зависимостью, но вы можете настроить прямые зависимости для использования работоспособной версии косвенной зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-206">Your conflict is with an indirect dependency, but you can configure your direct dependencies to use a workable indirect dependency version.</span></span>
- <span data-ttu-id="19fb6-207">Вы знаете конфликтующую версию и можете быть уверены, что она не изменится.</span><span class="sxs-lookup"><span data-stu-id="19fb6-207">You know the conflicting version and can rely on it not changing.</span></span>

<span data-ttu-id="19fb6-208">Пакет `Newtonsoft.Json` — хороший пример последнего сценария.</span><span class="sxs-lookup"><span data-stu-id="19fb6-208">The `Newtonsoft.Json` package is a good example of this last scenario.</span></span> <span data-ttu-id="19fb6-209">Это зависимость в PowerShell 6 и более поздних версий, которая не используется в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-209">This is a dependency of PowerShell 6 and above, and isn't used in Windows PowerShell.</span></span> <span data-ttu-id="19fb6-210">Простой способ разрешения конфликтов версий — использовать минимальную версию `Newtonsoft.Json` в нужных версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-210">Meaning a simple way to resolve versioning conflicts is to target the lowest version of `Newtonsoft.Json` across the PowerShell versions you wish to target.</span></span>

<span data-ttu-id="19fb6-211">Например, PowerShell 6.2.6 и PowerShell 7.0.2 в настоящее время используют `Newtonsoft.Json` версии 12.0.3.</span><span class="sxs-lookup"><span data-stu-id="19fb6-211">For example, PowerShell 6.2.6 and PowerShell 7.0.2 both currently use `Newtonsoft.Json` version 12.0.3.</span></span> <span data-ttu-id="19fb6-212">Таким образом, чтобы создать модуль, предназначенный для Windows PowerShell, PowerShell 6 и PowerShell 7, нужно выбрать `Newtonsoft.Json 12.0.3` в качестве зависимости и включить его в созданный модуль.</span><span class="sxs-lookup"><span data-stu-id="19fb6-212">So, to create a module targeting Windows PowerShell, PowerShell 6, and PowerShell 7, you would target `Newtonsoft.Json 12.0.3` as a dependency and include it in your built module.</span></span> <span data-ttu-id="19fb6-213">При загрузке модуля в PowerShell 6 или 7 собственная сборка `Newtonsoft.Json` PowerShell уже загружена.</span><span class="sxs-lookup"><span data-stu-id="19fb6-213">When the module is loaded in PowerShell 6 or 7, PowerShell's own `Newtonsoft.Json` assembly is already loaded.</span></span> <span data-ttu-id="19fb6-214">Кроме того, это как минимум версия, необходимая для вашего модуля, поэтому разрешение будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="19fb6-214">Also, it is at least the version required for your module, so resolution succeeds.</span></span> <span data-ttu-id="19fb6-215">В Windows PowerShell эта сборка еще отсутствует в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-215">In Windows PowerShell, the assembly isn't already present in PowerShell.</span></span> <span data-ttu-id="19fb6-216">Вместо этого она загружается из папки модуля.</span><span class="sxs-lookup"><span data-stu-id="19fb6-216">So, it's loaded from your module folder instead.</span></span>

<span data-ttu-id="19fb6-217">Как правило, при выборе конкретного пакета PowerShell, например `Microsoft.PowerShell.Sdk` или `System.Management.Automation`, NuGet должен иметь возможность разрешить нужные версии зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-217">Generally, when targeting a concrete PowerShell package, like `Microsoft.PowerShell.Sdk` or `System.Management.Automation`, NuGet should be able to resolve the right dependency versions required.</span></span> <span data-ttu-id="19fb6-218">Настроить нацеливание одновременно на Windows PowerShell и PowerShell 6+ сложнее, поскольку необходимо выбрать между нацеливанием на несколько платформ и `PowerShellStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-218">Targeting both Windows PowerShell and PowerShell 6+ becomes more difficult because you must choose between targeting multiple frameworks or `PowerShellStandard.Library`.</span></span>

<span data-ttu-id="19fb6-219">Использование общей версии не работает в следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="19fb6-219">Circumstances where pinning to a common dependency version won't work include:</span></span>

- <span data-ttu-id="19fb6-220">Конфликт связан с косвенной зависимостью, и ни одну из зависимостей нельзя настроить для использования общей версии.</span><span class="sxs-lookup"><span data-stu-id="19fb6-220">The conflict is with an indirect dependency, and none of your dependencies can be configured to use a common version.</span></span>
- <span data-ttu-id="19fb6-221">Другая версия зависимости часто меняется, поэтому выбор общей версии поможет лишь на время.</span><span class="sxs-lookup"><span data-stu-id="19fb6-221">The other dependency version is likely to change often, so settling on a common version is only a short-term fix.</span></span>

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a><span data-ttu-id="19fb6-222">Добавление обработчика событий AssemblyResolve для создания динамического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="19fb6-222">Add an AssemblyResolve event handler to create a dynamic binding redirect</span></span>

<span data-ttu-id="19fb6-223">Иногда изменить свою версию зависимости невозможно или слишком сложно.</span><span class="sxs-lookup"><span data-stu-id="19fb6-223">Sometimes changing your own dependency version isn't possible or is too difficult.</span></span> <span data-ttu-id="19fb6-224">Другой вариант — настроить перенаправление динамической привязки, зарегистрировав обработчик событий для события `AssemblyResolve`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-224">Another option is to set up a dynamic binding redirect by registering an event handler for the `AssemblyResolve` event.</span></span>

<span data-ttu-id="19fb6-225">Как и в случае с перенаправлением статической привязки, нужно заставить всех потребителей зависимости использовать одну и ту же фактическую сборку.</span><span class="sxs-lookup"><span data-stu-id="19fb6-225">As with a static binding redirect, the point is to force all consumers of a dependency to use the same actual assembly.</span></span> <span data-ttu-id="19fb6-226">Вы перехватываете вызовы для загрузки зависимости и всегда перенаправляете их в нужную версию.</span><span class="sxs-lookup"><span data-stu-id="19fb6-226">You intercept calls to load the dependency and always redirect them to the version you want.</span></span>

<span data-ttu-id="19fb6-227">Это выглядит примерно так.</span><span class="sxs-lookup"><span data-stu-id="19fb6-227">This looks something like this:</span></span>

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

<span data-ttu-id="19fb6-228">Конечно, вы могли бы зарегистрировать блок сценария в PowerShell, чтобы обрабатывать событие `AssemblyResolve`, но:</span><span class="sxs-lookup"><span data-stu-id="19fb6-228">You can technically register a scriptblock within PowerShell to handle an `AssemblyResolve` event, but:</span></span>

- <span data-ttu-id="19fb6-229">Событие `AssemblyResolve` может быть запущено в любом потоке, и PowerShell тут бессилен.</span><span class="sxs-lookup"><span data-stu-id="19fb6-229">An `AssemblyResolve` event may be triggered on any thread, something that PowerShell will be unable to handle.</span></span>
- <span data-ttu-id="19fb6-230">Даже если события обрабатываются в правильном потоке, область действия PowerShell требует внимательного написания блока сценариев обработчика событий, чтобы не зависеть от переменных, определенных за его пределами.</span><span class="sxs-lookup"><span data-stu-id="19fb6-230">Even when events are handled on the right thread, PowerShell's scoping concepts mean that the event handler scriptblock must be written carefully to not depend on variables defined outside it.</span></span>

<span data-ttu-id="19fb6-231">В некоторых ситуациях перенаправление на общую версию не будет работать.</span><span class="sxs-lookup"><span data-stu-id="19fb6-231">There are situations where redirecting to a common version won't work:</span></span>

- <span data-ttu-id="19fb6-232">Если зависимость имеет критические изменения между версиями или если зависимый код использует функции, недоступные в версии, к которой выполняется перенаправление.</span><span class="sxs-lookup"><span data-stu-id="19fb6-232">When the dependency has made breaking changes between versions, or when dependent code relies on a functionality otherwise not available in the version you redirect to.</span></span>
- <span data-ttu-id="19fb6-233">Если модуль не загружен до конфликтующей зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-233">When your module isn't loaded before the conflicting dependency.</span></span> <span data-ttu-id="19fb6-234">Если вы регистрируете обработчик событий `AssemblyResolve` после загрузки зависимости, он никогда не будет срабатывать.</span><span class="sxs-lookup"><span data-stu-id="19fb6-234">If you register an `AssemblyResolve` event handler after the dependency has been loaded, it will never be fired.</span></span> <span data-ttu-id="19fb6-235">Если вы пытаетесь предотвратить конфликты зависимостей с другим модулем, это может быть проблематично в случае, когда другой модуль загружен первым.</span><span class="sxs-lookup"><span data-stu-id="19fb6-235">If you're trying to prevent dependency conflicts with another module, this may be an issue, since the other module may be loaded first.</span></span>

### <a name="use-the-dependency-out-of-process"></a><span data-ttu-id="19fb6-236">Использование зависимости вне процесса</span><span class="sxs-lookup"><span data-stu-id="19fb6-236">Use the dependency out of process</span></span>

<span data-ttu-id="19fb6-237">Это решение подходит скорее для пользователей, чем для авторов модулей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-237">This solution is more for module users than module authors.</span></span> <span data-ttu-id="19fb6-238">Это решение используется при взаимодействии с модулем, который не работает из-за существующего конфликта зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-238">This is a solution to use when confronted with a module that won't work due to an existing dependency conflict.</span></span>

<span data-ttu-id="19fb6-239">Конфликты зависимостей возникают, когда две версии одной сборки загружаются в один и тот же процесс .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-239">Dependency conflicts occur because two versions of the same assembly are loaded into the same .NET process.</span></span> <span data-ttu-id="19fb6-240">Простое решение — загрузить их в разные процессы, если вы по-прежнему сможете использовать эти функции одновременно.</span><span class="sxs-lookup"><span data-stu-id="19fb6-240">A simple solution is to load them into different processes, as long as you can still use the functionality from both together.</span></span>

<span data-ttu-id="19fb6-241">В PowerShell это можно сделать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="19fb6-241">In PowerShell, there are several ways to achieve this:</span></span>

- <span data-ttu-id="19fb6-242">Вызов PowerShell в качестве подпроцесса</span><span class="sxs-lookup"><span data-stu-id="19fb6-242">Invoke PowerShell as a subprocess</span></span>

  <span data-ttu-id="19fb6-243">Простой способ выполнить команду PowerShell вне текущего процесса — запустить новый процесс PowerShell непосредственно с помощью вызова команды:</span><span class="sxs-lookup"><span data-stu-id="19fb6-243">A simple way to run a PowerShell command out of the current process is to just start a new PowerShell process directly with the command call:</span></span>

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  <span data-ttu-id="19fb6-244">Основное ограничение заключается в том, что реструктуризация результата может быть сложнее или более подвержена ошибкам, чем другие варианты.</span><span class="sxs-lookup"><span data-stu-id="19fb6-244">The main limitation here is that restructuring the result can be trickier or more error prone than other options.</span></span>

- <span data-ttu-id="19fb6-245">Система заданий PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fb6-245">The PowerShell job system</span></span>

  <span data-ttu-id="19fb6-246">Система заданий PowerShell также выполняет команды вне процесса, отправляя команды новому процессу PowerShell и возвращая результаты.</span><span class="sxs-lookup"><span data-stu-id="19fb6-246">The PowerShell job system also runs commands out of process, by sending commands to a new PowerShell process and returning the results:</span></span>

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  <span data-ttu-id="19fb6-247">В этом случае необходимо только убедиться, что все переменные и состояние передаются правильно.</span><span class="sxs-lookup"><span data-stu-id="19fb6-247">In this case, you just need to be sure that any variables and state are passed in correctly.</span></span>

  <span data-ttu-id="19fb6-248">Система заданий также может быть несколько громоздкой при выполнении небольших команд.</span><span class="sxs-lookup"><span data-stu-id="19fb6-248">The job system can also be slightly cumbersome when running small commands.</span></span>

- <span data-ttu-id="19fb6-249">Удаленное взаимодействие PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fb6-249">PowerShell remoting</span></span>

  <span data-ttu-id="19fb6-250">Если удаленное взаимодействие с PowerShell доступно, это может оказаться удобным вариантом выполнения команд вне процесса.</span><span class="sxs-lookup"><span data-stu-id="19fb6-250">When it's available, PowerShell remoting can be a useful way to run commands out of process.</span></span> <span data-ttu-id="19fb6-251">При удаленном взаимодействии можно создать новый сеанс **PSSession** в новом процессе, вызвать его команды через удаленное взаимодействие с PowerShell, а затем использовать результаты локально с другими модулями, содержащими конфликтующие зависимости.</span><span class="sxs-lookup"><span data-stu-id="19fb6-251">With remoting, you can create a fresh **PSSession** in a new process, call its commands over PowerShell remoting, then use the results locally with the other modules containing the conflicting dependencies.</span></span>

  <span data-ttu-id="19fb6-252">Пример может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-252">An example might look like this:</span></span>

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- <span data-ttu-id="19fb6-253">Неявное удаленное взаимодействие с Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fb6-253">Implicit remoting to Windows PowerShell</span></span>

  <span data-ttu-id="19fb6-254">Еще один вариант в PowerShell 7 — использовать флаг `-UseWindowsPowerShell` в `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-254">Another option in PowerShell 7 is to use the `-UseWindowsPowerShell` flag on `Import-Module`.</span></span> <span data-ttu-id="19fb6-255">При этом модуль будет импортирован через локальный сеанс удаленного взаимодействия в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-255">This will import the module through a local remoting session into Windows PowerShell:</span></span>

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  <span data-ttu-id="19fb6-256">Имейте в виду, что модули могут не работать с Windows PowerShell или работать иначе.</span><span class="sxs-lookup"><span data-stu-id="19fb6-256">Be aware that modules may not work with, or work differently with Windows PowerShell.</span></span>

#### <a name="when-out-of-process-invocation-should-not-be-used"></a><span data-ttu-id="19fb6-257">Когда не следует использовать вызов вне процесса</span><span class="sxs-lookup"><span data-stu-id="19fb6-257">When out-of-process invocation should not be used</span></span>

<span data-ttu-id="19fb6-258">Авторам модуля сложно внедрить в модуль вызов команды вне процесса, и в некоторых случаях могут возникать проблемы.</span><span class="sxs-lookup"><span data-stu-id="19fb6-258">As a module author, out-of-process command invocation is difficult to bake into a module and may have edge cases that cause issues.</span></span> <span data-ttu-id="19fb6-259">В частности, удаленное взаимодействие и задания могут быть недоступны во всех средах, где должен работать ваш модуль.</span><span class="sxs-lookup"><span data-stu-id="19fb6-259">In particular, remoting and jobs may not be available in all environments where your module needs to work.</span></span> <span data-ttu-id="19fb6-260">Но вы по-прежнему можете применять общий принцип перемещения реализации за пределы процесса и перевод модуля PowerShell в разряд более тонких клиентов.</span><span class="sxs-lookup"><span data-stu-id="19fb6-260">However, the general principle of moving the implementation out of process and allowing the PowerShell module to be a thinner client, may still be applicable.</span></span>

<span data-ttu-id="19fb6-261">Иногда пользователи модуля не могут использовать вызов вне процесса.</span><span class="sxs-lookup"><span data-stu-id="19fb6-261">As a module user, there are cases where out-of-process invocation won't work:</span></span>

- <span data-ttu-id="19fb6-262">Если удаленное взаимодействие с PowerShell недоступно из-за отсутствия у вас привилегий или отключено.</span><span class="sxs-lookup"><span data-stu-id="19fb6-262">When PowerShell remoting is unavailable because you don't have privileges to use it or it is not enabled.</span></span>
- <span data-ttu-id="19fb6-263">Если в качестве входных данных для метода или другой команды требуется определенный тип .NET в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="19fb6-263">When a particular .NET type is needed from output as input to a method or another command.</span></span>
  <span data-ttu-id="19fb6-264">Команды, выполняемые через удаленное взаимодействие с PowerShell, создают десериализованные объекты, а не строго типизированные объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-264">Commands running over PowerShell remoting emit deserialized objects rather than strongly-typed .NET objects.</span></span> <span data-ttu-id="19fb6-265">Это означает, что вызовы методов и строго типизированные API не работают с выходными данными команд, импортированных через удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="19fb6-265">This means that method calls and strongly typed APIs do not work with the output of commands imported over remoting.</span></span>

## <a name="more-robust-solutions"></a><span data-ttu-id="19fb6-266">Более надежные решения</span><span class="sxs-lookup"><span data-stu-id="19fb6-266">More robust solutions</span></span>

<span data-ttu-id="19fb6-267">У всех предыдущих решений существуют исключения и ограничения,</span><span class="sxs-lookup"><span data-stu-id="19fb6-267">The previous solutions all had scenarios and modules that don't work.</span></span> <span data-ttu-id="19fb6-268">при этом их относительно просто реализовать.</span><span class="sxs-lookup"><span data-stu-id="19fb6-268">However, they also have the virtue of being relatively simple to implement correctly.</span></span> <span data-ttu-id="19fb6-269">Следующие решения являются более надежными, но для их правильной реализации требуются дополнительные усилия и, если они не до конца продуманы, могут возникать незаметные ошибки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-269">The following solutions are more robust, but require more effort to implement correctly and can introduce subtle bugs if not written carefully.</span></span>

### <a name="loading-through-net-core-assembly-load-contexts"></a><span data-ttu-id="19fb6-270">Загрузка с помощью контекстов загрузки сборок .NET Core</span><span class="sxs-lookup"><span data-stu-id="19fb6-270">Loading through .NET Core Assembly Load Contexts</span></span>

<span data-ttu-id="19fb6-271">[Контексты загрузки сборок](/dotnet/api/system.runtime.loader.assemblyloadcontext) в качестве реализуемого API были представлены в .NET Core 1.0 специально для того, чтобы устранить необходимость загрузки нескольких версий одной сборки в одну и ту же среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="19fb6-271">[Assembly Load Contexts](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) as an implementable API were introduced in .NET Core 1.0 to specifically address the need to load multiple versions of the same assembly into the same runtime.</span></span>

<span data-ttu-id="19fb6-272">В .NET Core и .NET 5 они являются самым надежным решением проблемы загрузки конфликтующих версий сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-272">Within .NET Core and .NET 5, they offer the most robust solution to the problem of loading conflicting versions of an assembly.</span></span> <span data-ttu-id="19fb6-273">Однако пользовательские контексты загрузки сборок недоступны в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19fb6-273">However, custom ALCs are not available in .NET Framework.</span></span> <span data-ttu-id="19fb6-274">Это означает, что решение работает только в PowerShell 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="19fb6-274">This means that this solution only works in PowerShell 6 and above.</span></span>

<span data-ttu-id="19fb6-275">В настоящее время лучший пример использования контекстов загрузки сборок для изоляции зависимостей в PowerShell представлен в службах редактора PowerShell, языковом сервере для расширения PowerShell для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="19fb6-275">Currently, the best example of using an ALC for dependency isolation in PowerShell is in PowerShell Editor Services, the language server for the PowerShell extension for Visual Studio Code.</span></span> <span data-ttu-id="19fb6-276">[Контекст загрузки сборок используется](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs), чтобы предотвратить конфликт собственных зависимостей служб редактора PowerShell с зависимостями в модулях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-276">An [ALC is used](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) to prevent PowerShell Editor Services' own dependencies from clashing with those in PowerShell modules.</span></span>

<span data-ttu-id="19fb6-277">Реализовать изоляцию зависимостей модулей с помощью контекста загрузки сборок довольно сложно, но мы рассмотрим простейший пример.</span><span class="sxs-lookup"><span data-stu-id="19fb6-277">Implementing module dependency isolation with an ALC is conceptually difficult, but we will work through a minimal example.</span></span> <span data-ttu-id="19fb6-278">Представьте, что у нас есть простой модуль, предназначенный только для работы с PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="19fb6-278">Imagine we have a simple module that is only intended to work in PowerShell 7.</span></span>
<span data-ttu-id="19fb6-279">Исходный код организован следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-279">The source code is organized as follows:</span></span>

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

<span data-ttu-id="19fb6-280">Реализация командлета выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-280">The cmdlet implementation looks like this:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="19fb6-281">Манифест (в очень упрощенном виде) выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-281">The (heavily simplified) manifest, looks like this:</span></span>

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

<span data-ttu-id="19fb6-282">А `csproj` выглядит так.</span><span class="sxs-lookup"><span data-stu-id="19fb6-282">And the `csproj` looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="19fb6-283">При сборке этого модуля создаются выходные данные на основе следующего макета.</span><span class="sxs-lookup"><span data-stu-id="19fb6-283">When we build this module, the generated output has the following layout:</span></span>

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

<span data-ttu-id="19fb6-284">В этом примере наша проблема находится в сборке `Shared.Dependency.dll`, которая является нашей воображаемой конфликтующей зависимостью.</span><span class="sxs-lookup"><span data-stu-id="19fb6-284">In this example, our problem is in the `Shared.Dependency.dll` assembly, which is our imaginary conflicting dependency.</span></span> <span data-ttu-id="19fb6-285">Это зависимость, которую необходимо разместить за контекстом загрузки сборок, чтобы мы могли использовать версию для конкретного модуля.</span><span class="sxs-lookup"><span data-stu-id="19fb6-285">This is the dependency that we need to put behind an ALC so that we can use the module-specific version.</span></span>

<span data-ttu-id="19fb6-286">Необходимо перестроить модуль таким образом, чтобы:</span><span class="sxs-lookup"><span data-stu-id="19fb6-286">We need to re-engineer the module so that:</span></span>

- <span data-ttu-id="19fb6-287">Зависимости модуля загружаются только в пользовательский контекст загрузки сборок, а не в контекст PowerShell, чтобы конфликтов не возникало.</span><span class="sxs-lookup"><span data-stu-id="19fb6-287">Module dependencies are only loaded into our custom ALC, and not into PowerShell's ALC, so there can be no conflict.</span></span> <span data-ttu-id="19fb6-288">Кроме того, по мере добавления зависимостей в проект мы не хотим постоянно добавлять код для поддержания работоспособности загрузки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-288">Moreover, as we add more dependencies to our project, we don't want to continuously add more code to keep loading working.</span></span> <span data-ttu-id="19fb6-289">Вместо этого мы хотим использовать многоразовую универсальную логику разрешения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-289">Instead, we want reusable, generic dependency resolution logic.</span></span>
- <span data-ttu-id="19fb6-290">Загрузка модуля в PowerShell по-прежнему работает нормально.</span><span class="sxs-lookup"><span data-stu-id="19fb6-290">Loading the module still works as normal in PowerShell.</span></span> <span data-ttu-id="19fb6-291">Командлеты и другие типы, необходимые системе модуля PowerShell, определяются в собственном контексте загрузки сборок в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-291">Cmdlets and other types that the PowerShell module system needs are defined within PowerShell's own ALC.</span></span>

<span data-ttu-id="19fb6-292">Чтобы удовлетворить эти два требования, необходимо разделить модуль на две сборки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-292">To mediate these two requirements, we must break up our module into two assemblies:</span></span>

- <span data-ttu-id="19fb6-293">Сборка командлетов, `AlcModule.Cmdlets.dll`, содержащая определения всех типов, необходимых системе модуля PowerShell для правильной загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="19fb6-293">A cmdlets assembly, `AlcModule.Cmdlets.dll`, that contains definitions of all the types that PowerShell's module system needs to load our module correctly.</span></span> <span data-ttu-id="19fb6-294">А именно: любые реализации базового класса `Cmdlet` и класса, реализующего `IModuleAssemblyInitializer`, который настраивает обработчик событий для `AssemblyLoadContext.Default.Resolving` для правильной загрузки `AlcModule.Engine.dll` через пользовательский контекст загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-294">Namely, any implementations of the `Cmdlet` base class and the class that implements `IModuleAssemblyInitializer`, which sets up the event handler for `AssemblyLoadContext.Default.Resolving` to properly load `AlcModule.Engine.dll` through our custom ALC.</span></span> <span data-ttu-id="19fb6-295">Поскольку в PowerShell 7 намеренно скрываются типы, определенные в сборках, загруженных в других контекстах загрузки сборок, все типы, которые должны быть общедоступными для PowerShell, также следует определить здесь.</span><span class="sxs-lookup"><span data-stu-id="19fb6-295">Since PowerShell 7 deliberately hides types defined in assemblies loaded in other ALCs, any types that are meant to be publicly exposed to PowerShell must also be defined here.</span></span> <span data-ttu-id="19fb6-296">Наконец, в этой сборке необходимо указать определение пользовательского контекста загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-296">Finally, our custom ALC definition needs to be defined in this assembly.</span></span> <span data-ttu-id="19fb6-297">Кроме того, в этой сборке должно быть как можно меньше кода.</span><span class="sxs-lookup"><span data-stu-id="19fb6-297">Beyond that, as little code as possible should live in this assembly.</span></span>
- <span data-ttu-id="19fb6-298">Сборка обработчика `AlcModule.Engine.dll`, которая обрабатывает фактическую реализацию модуля.</span><span class="sxs-lookup"><span data-stu-id="19fb6-298">An engine assembly, `AlcModule.Engine.dll`, that handles the actual implementation of the module.</span></span>
  <span data-ttu-id="19fb6-299">Ее типы доступны в контексте загрузки сборок PowerShell, но изначально мы выполняем загрузку с помощью нашего пользовательского контекста загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-299">Types from this are available in the PowerShell ALC, but it will initially be loaded through our custom ALC.</span></span> <span data-ttu-id="19fb6-300">Зависимости загружаются только в пользовательский контекст загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-300">Its dependencies are only loaded into the custom ALC.</span></span> <span data-ttu-id="19fb6-301">По сути, это что-то вроде _моста_ между двумя контекстами загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-301">Effectively, this becomes a _bridge_ between the two ALCs.</span></span>

<span data-ttu-id="19fb6-302">Если продолжить сравнение с мостом, можно нарисовать следующую схему.</span><span class="sxs-lookup"><span data-stu-id="19fb6-302">Using this bridge concept, our new assembly situation looks like this:</span></span>

![Схема, представляющая AlcModule.Engine.dll как мост между двумя контекстами загрузки сборок](./media/resolving-dependency-conflicts/alc-diagram.jpg)

<span data-ttu-id="19fb6-304">Чтобы убедиться, что логика проверки зависимостей в контексте загрузки сборок по умолчанию не разрешает загрузку зависимостей в пользовательский контекст загрузки сборок, необходимо разделить эти две части модуля на разные каталоги.</span><span class="sxs-lookup"><span data-stu-id="19fb6-304">To make sure the default ALC's dependency probing logic does not resolve the dependencies to be loaded into the custom ALC, we need to separate these two parts of the module in different directories.</span></span> <span data-ttu-id="19fb6-305">Новый макет модуля имеет следующую структуру.</span><span class="sxs-lookup"><span data-stu-id="19fb6-305">The new module layout has the following structure:</span></span>

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

<span data-ttu-id="19fb6-306">Чтобы увидеть, как изменяется реализация, мы начнем с реализации `AlcModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-306">To see how the implementation changes, we'll start with the implementation of `AlcModule.Engine.dll`:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

<span data-ttu-id="19fb6-307">Это простой контейнер для зависимости, `Shared.Dependency.dll`, но его следует рассматривать как API .NET для функций, для которых командлеты в другой сборке служат оболочкой в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-307">This is a simple container for the dependency, `Shared.Dependency.dll`, but you should think of it as the .NET API for your functionality that the cmdlets in the other assembly wrap for PowerShell.</span></span>

<span data-ttu-id="19fb6-308">Командлет в `AlcModule.Cmdlets.dll` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-308">The cmdlet in `AlcModule.Cmdlets.dll` looks like this:</span></span>

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="19fb6-309">На этом этапе, если нужно загрузить **AlcModule** и запустить `Test-AlcModule`, мы получаем `FileNotFoundException`, когда контекст загрузки сборок по умолчанию пытается загрузить `Alc.Engine.dll` для выполнения `EndProcessing()`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-309">At this point, if we were to load **AlcModule** and run `Test-AlcModule`, we get a `FileNotFoundException` when the default ALC tries to load `Alc.Engine.dll` to run `EndProcessing()`.</span></span> <span data-ttu-id="19fb6-310">Это хорошо, так как это означает, что по умолчанию контекст загрузки сборок не может найти зависимости, которые мы хотим скрыть.</span><span class="sxs-lookup"><span data-stu-id="19fb6-310">This is good, since it means the default ALC can't find the dependencies we want to hide.</span></span>

<span data-ttu-id="19fb6-311">Теперь необходимо добавить код в `AlcModule.Cmdlets.dll`, чтобы он "знал", как разрешать `AlcModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-311">Now we need to add code to `AlcModule.Cmdlets.dll` so that it knows how to resolve `AlcModule.Engine.dll`.</span></span> <span data-ttu-id="19fb6-312">Сначала необходимо определить пользовательский контекст загрузки сборок, который будет разрешать сборки из каталога модуля `Dependencies`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-312">First we must define our custom ALC that will resolve assemblies from our module's `Dependencies` directory:</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _depdendencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                s_dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

<span data-ttu-id="19fb6-313">Затем необходимо подключить пользовательский контекст загрузки сборок к событию `Resolving` по умолчанию, которое является версией события `AssemblyResolve` контекста загрузки сборок для доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="19fb6-313">Then we need to hook up our custom ALC to the default ALC's `Resolving` event, which is the ALC version of the `AssemblyResolve` event on Application Domains.</span></span> <span data-ttu-id="19fb6-314">Это событие срабатывает для поиска `AlcModule.Engine.dll` при вызове `EndProcessing()`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-314">This event is fired to find `AlcModule.Engine.dll` when `EndProcessing()` is called.</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

<span data-ttu-id="19fb6-315">В новой реализации рассмотрим последовательность вызовов при загрузке модуля и запуске `Test-AlcModule`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-315">With the new implementation, take a look at the sequence of calls that occurs when the module is loaded and `Test-AlcModule` is run:</span></span>

![Схема последовательности вызовов, использующих пользовательский контекст загрузки сборок для загрузки зависимостей](./media/resolving-dependency-conflicts/alc-sequence.png)

<span data-ttu-id="19fb6-317">На что нужно обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="19fb6-317">Some points of interest are:</span></span>

- <span data-ttu-id="19fb6-318">`IModuleAssemblyInitializer` выполняется первым, когда модуль загружает и настраивает событие `Resolving`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-318">The `IModuleAssemblyInitializer` is run first when the module loads and sets the `Resolving` event.</span></span>
- <span data-ttu-id="19fb6-319">Мы не загружаем зависимости, пока не запустится `Test-AlcModule` и не будет вызван метод `EndProcessing()`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-319">We don't load the dependencies until `Test-AlcModule` is run and its `EndProcessing()` method is called.</span></span>
- <span data-ttu-id="19fb6-320">При вызове `EndProcessing()` контекст загрузки сборок по умолчанию не находит `AlcModule.Engine.dll` и запускает событие `Resolving`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-320">When `EndProcessing()` is called, the default ALC fails to find `AlcModule.Engine.dll` and fires the `Resolving` event.</span></span>
- <span data-ttu-id="19fb6-321">Наш обработчик событий привязывает пользовательский контекст загрузки сборок к контексту загрузки сборок по умолчанию и загружает только `AlcModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-321">Our event handler hooks up the custom ALC to the default ALC and loads `AlcModule.Engine.dll` only.</span></span>
- <span data-ttu-id="19fb6-322">При вызове `AlcEngine.Use()` в `AlcModule.Engine.dll` пользовательский контекст загрузки сборок снова запускается для разрешения `Shared.Dependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-322">When `AlcEngine.Use()` is called within `AlcModule.Engine.dll`, the custom ALC again kicks in to resolve `Shared.Dependency.dll`.</span></span> <span data-ttu-id="19fb6-323">В частности, он всегда загружает _нашу_ библиотеку `Shared.Dependency.dll`, поскольку она никогда не конфликтует с содержимым контекста загрузки сборок по умолчанию и просматривает только наш каталог `Dependencies`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-323">Specifically, it always loads _our_ `Shared.Dependency.dll` since it never conflicts with anything in the default ALC and only looks in our `Dependencies` directory.</span></span>

<span data-ttu-id="19fb6-324">При сборке реализации новый макет исходного кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-324">Assembling the implementation, our new source code layout looks like this:</span></span>

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

<span data-ttu-id="19fb6-325">AlcModule.Cmdlets.csproj:</span><span class="sxs-lookup"><span data-stu-id="19fb6-325">AlcModule.Cmdlets.csproj looks like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="19fb6-326">AlcModule.Engine.csproj:</span><span class="sxs-lookup"><span data-stu-id="19fb6-326">AlcModule.Engine.csproj looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="19fb6-327">Итак, наши действия при сборке модуля будут следующими.</span><span class="sxs-lookup"><span data-stu-id="19fb6-327">So, when we build the module, our strategy is:</span></span>

- <span data-ttu-id="19fb6-328">Выполнить сборку `AlcModule.Engine`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-328">Build `AlcModule.Engine`</span></span>
- <span data-ttu-id="19fb6-329">Выполнить сборку `AlcModule.Cmdlets`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-329">Build `AlcModule.Cmdlets`</span></span>
- <span data-ttu-id="19fb6-330">Скопировать все из `AlcModule.Engine` в каталог `Dependencies` и запомнить, что мы скопировали.</span><span class="sxs-lookup"><span data-stu-id="19fb6-330">Copy everything from `AlcModule.Engine` into the `Dependencies` directory, and remember what we copied</span></span>
- <span data-ttu-id="19fb6-331">Скопировать все из `AlcModule.Cmdlets`, чего не было в `AlcModule.Engine`, в каталог базового модуля.</span><span class="sxs-lookup"><span data-stu-id="19fb6-331">Copy everything from `AlcModule.Cmdlets` that wasn't in `AlcModule.Engine` into the base module directory</span></span>

<span data-ttu-id="19fb6-332">Так как структура модуля очень важна для разделения зависимостей, используйте следующий сценарий сборки из корневого каталога источника.</span><span class="sxs-lookup"><span data-stu-id="19fb6-332">Since the module layout here is so crucial to dependency separation, here's a build script to use from the source root:</span></span>

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

<span data-ttu-id="19fb6-333">Наконец, у нас есть общий способ использовать контекст загрузки сборок для изоляции зависимостей модуля, который не теряет надежности по мере добавления дополнительных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-333">Finally, we have a general way to use an Assembly Load Context to isolate our module's dependencies that remains robust over time as more dependencies are added.</span></span>

<span data-ttu-id="19fb6-334">Более подробный пример вы найдете в этом [репозитории GitHub](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span><span class="sxs-lookup"><span data-stu-id="19fb6-334">For a more detailed example, go to this [GitHub repository](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span></span> <span data-ttu-id="19fb6-335">В этом примере показано, как перенести модуль для использования контекста загрузки сборок, сохранив работоспособность этого модуля в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19fb6-335">This example demonstrates how to migrate a module to use an ALC, while keeping that module working in .NET Framework.</span></span> <span data-ttu-id="19fb6-336">Здесь также показано, как использовать .NET Standard и PowerShell Standard для упрощения основной реализации.</span><span class="sxs-lookup"><span data-stu-id="19fb6-336">It also show how to use .NET Standard and PowerShell Standard to simplify the core implementation.</span></span>

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a><span data-ttu-id="19fb6-337">Обработчик разрешения сборки для параллельной загрузки с помощью `Assembly.LoadFile()`</span><span class="sxs-lookup"><span data-stu-id="19fb6-337">Assembly resolve handler for side-by-side loading with `Assembly.LoadFile()`</span></span>

<span data-ttu-id="19fb6-338">Еще один, возможно, более простой способ достижения параллельной загрузки сборок заключается в подключении события `AssemblyResolve` к `Assembly.LoadFile()`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-338">Another, possibly simpler, way to achieve side-by-side assembly loading is to hook up an `AssemblyResolve` event to `Assembly.LoadFile()`.</span></span> <span data-ttu-id="19fb6-339">Преимущество использования `Assembly.LoadFile()` заключается в том, что это решение проще всего реализовать и оно подходит как для .NET Core, так и для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19fb6-339">Using `Assembly.LoadFile()` has the advantage of being the simplest solution to implement and works with both .NET Core and .NET Framework.</span></span>

<span data-ttu-id="19fb6-340">Чтобы продемонстрировать это, давайте рассмотрим краткий пример реализации, объединяющей идеи из нашего примера перенаправления динамической привязки и примера контекста загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-340">To show this, let's take a look at a quick example of an implementation that combines ideas from our dynamic binding redirect example, and the Assembly Load Context example above.</span></span>

<span data-ttu-id="19fb6-341">Мы вызовем модуль **LoadFileModule** с простой командой `Test-LoadFile [-Path] <path>`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-341">We'll call this module **LoadFileModule**, which has a trivial command `Test-LoadFile [-Path] <path>`.</span></span> <span data-ttu-id="19fb6-342">Этот модуль принимает зависимость от сборки `CsvHelper` (версия 15.0.5).</span><span class="sxs-lookup"><span data-stu-id="19fb6-342">This module takes a dependency on the `CsvHelper` assembly (version 15.0.5).</span></span>

<span data-ttu-id="19fb6-343">Как и в случае с модулем контекста загрузки сборок, сначала необходимо разделить модуль на две части.</span><span class="sxs-lookup"><span data-stu-id="19fb6-343">As with the ALC module, we must first split up the module into two pieces.</span></span>

<span data-ttu-id="19fb6-344">Первая часть выполняет фактическую реализацию `LoadFileModule.Engine`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-344">The first part does the actual implementation, `LoadFileModule.Engine`:</span></span>

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

<span data-ttu-id="19fb6-345">Вторая часть — это то, что PowerShell загружает напрямую, `LoadFileModule.Cmdlets`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-345">The second part is what PowerShell loads directly, `LoadFileModule.Cmdlets`.</span></span> <span data-ttu-id="19fb6-346">Мы используем стратегию, похожую на модуль контекста загрузки сборок, где мы изолируем зависимости в отдельном каталоге.</span><span class="sxs-lookup"><span data-stu-id="19fb6-346">We use a strategy similar to the ALC module, where we isolate dependencies in a separate directory.</span></span> <span data-ttu-id="19fb6-347">Но на этот раз мы загружаем все сборки с событием разрешения, а не просто библиотеку `LoadFileModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-347">But this time, we load all assemblies in with a resolve event rather than just `LoadFileModule.Engine.dll`.</span></span>

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

<span data-ttu-id="19fb6-348">Наконец, макет модуля аналогичен модулю контекста загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="19fb6-348">Finally, the layout of the module is also similar to the ALC module:</span></span>

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

<span data-ttu-id="19fb6-349">В этой структуре **LoadFileModule** теперь можно загружать вместе с другими модулями с зависимостью от **CsvHelper**.</span><span class="sxs-lookup"><span data-stu-id="19fb6-349">With this structure in place, **LoadFileModule** now supports being loaded alongside other modules with a dependency on **CsvHelper**.</span></span>

<span data-ttu-id="19fb6-350">Так как наш обработчик применяется ко **всем** событиям `AssemblyResolve` в домене приложения, необходимо принять некоторые решения по проектированию.</span><span class="sxs-lookup"><span data-stu-id="19fb6-350">Because our handler applies to **all** `AssemblyResolve` events across the Application Domain, we need to make some specific design choices here:</span></span>

- <span data-ttu-id="19fb6-351">Чтобы сузить интервал, в котором наше событие может помешать другой загрузке, мы начинаем обработку общей загрузки зависимостей только после загрузки `LoadFileModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-351">To narrow the window in which our event may interfere with other loading, we only start handling general dependency loading after `LoadFileModule.Engine.dll` has been loaded.</span></span>
- <span data-ttu-id="19fb6-352">Мы отправим `LoadFileModule.Engine.dll` в каталог зависимостей, чтобы он загружался вызовом `LoadFile()`, а не через PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-352">We push `LoadFileModule.Engine.dll` out into the Dependencies directory, so that it's loaded by a `LoadFile()` call rather than by PowerShell.</span></span> <span data-ttu-id="19fb6-353">Это означает, что собственные загрузки зависимостей всегда вызывают событие `AssemblyResolve`, даже если в PowerShell загружается другая библиотека `CsvHelper.dll` (например).</span><span class="sxs-lookup"><span data-stu-id="19fb6-353">This means its own dependency loads always raise an `AssemblyResolve` event, even if another `CsvHelper.dll` (for example) is loaded in PowerShell.</span></span>
  <span data-ttu-id="19fb6-354">Это дает нам возможность найти правильную зависимость.</span><span class="sxs-lookup"><span data-stu-id="19fb6-354">This gives us the opportunity to find the correct dependency.</span></span>
- <span data-ttu-id="19fb6-355">Так как мы должны разрешать только определенные зависимости для нашего модуля, мы вынуждены записать словарь имен и версий зависимостей в обработчике.</span><span class="sxs-lookup"><span data-stu-id="19fb6-355">Since we must only resolve the specific dependencies for our module, we're forced to code a dictionary of dependency names and versions into our handler.</span></span> <span data-ttu-id="19fb6-356">В нашем случае можно было бы использовать свойство `ResolveEventArgs.RequestingAssembly`, чтобы определить, запрашивается ли `CsvHelper` в нашем модуле.</span><span class="sxs-lookup"><span data-stu-id="19fb6-356">In our particular case, it would be possible to use the `ResolveEventArgs.RequestingAssembly` property to work out whether `CsvHelper` is being requested by our module.</span></span> <span data-ttu-id="19fb6-357">Но это не работает для зависимостей зависимостей. Например, если `CsvHelper` вызывает событие `AssemblyResolve`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-357">But this doesn't work for dependencies of dependencies; for example, if `CsvHelper` itself raised an `AssemblyResolve` event.</span></span> <span data-ttu-id="19fb6-358">Есть и другие, более трудные способы выполнить эту задачу, например сравнить запрошенные сборки с метаданными сборок в каталоге `Dependencies`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-358">There are other, harder ways to do this, such as comparing requested assemblies to the metadata of assemblies in the `Dependencies` directory.</span></span> <span data-ttu-id="19fb6-359">Но в этом примере мы сделали эту проверку более явной, чтобы выделить проблемы и упростить пример.</span><span class="sxs-lookup"><span data-stu-id="19fb6-359">But, in this example, we've made this checking more explicit to both highlight the issue and simplify the example.</span></span>

<span data-ttu-id="19fb6-360">Это ключевое различие между стратегией `LoadFile()` и использованием контекста загрузки сборок: событие `AssemblyResolve` должно обслуживать все нагрузки в домене приложения, поэтому нам гораздо сложнее изолировать наше разрешение зависимостей от других модулей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-360">This is the key difference between the `LoadFile()` strategy and the ALC strategy: the `AssemblyResolve` event must service all loads in the Application Domain, making it much harder to keep our dependency resolution from being tangled with other modules.</span></span> <span data-ttu-id="19fb6-361">Поскольку в .NET Framework отсутствуют контексты загрузки сборок, стоит разобраться в этом варианте.</span><span class="sxs-lookup"><span data-stu-id="19fb6-361">However, the lack of ALCs in .NET Framework makes this option worth understanding.</span></span>

### <a name="custom-application-domains"></a><span data-ttu-id="19fb6-362">Пользовательские домены приложений</span><span class="sxs-lookup"><span data-stu-id="19fb6-362">Custom Application Domains</span></span>

<span data-ttu-id="19fb6-363">Последний и самый крайний вариант изоляции сборок — использовать пользовательские домены приложений.</span><span class="sxs-lookup"><span data-stu-id="19fb6-363">The final and most extreme option for assembly isolation is to use custom Application Domains.</span></span>
<span data-ttu-id="19fb6-364">Домены приложений (во множественном числе) доступны только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19fb6-364">Application Domains (used in the plural) are only available in .NET Framework.</span></span> <span data-ttu-id="19fb6-365">Они используются для обеспечения внутрипроцессной изоляции между частями приложения .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-365">They are used to provide in-process isolation between parts of a .NET application.</span></span> <span data-ttu-id="19fb6-366">Одно из их применений — изоляция загрузки сборок друг от друга в рамках одного процесса.</span><span class="sxs-lookup"><span data-stu-id="19fb6-366">One of the uses is to isolate assembly loads from each other within the same process.</span></span>

<span data-ttu-id="19fb6-367">Однако домены приложений являются границами сериализации.</span><span class="sxs-lookup"><span data-stu-id="19fb6-367">However, Application Domains are serialization boundaries.</span></span> <span data-ttu-id="19fb6-368">На объекты в одном домене приложения нельзя ссылаться с помощью объектов в другом домене приложения. Кроме того, их нельзя использовать в другом домене.</span><span class="sxs-lookup"><span data-stu-id="19fb6-368">Objects in one Application Domain can't be referenced and used directly by objects in another Application Domain.</span></span> <span data-ttu-id="19fb6-369">Для решения этой проблемы можно реализовать `MarshalByRefObject`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-369">You can work around this by implementing `MarshalByRefObject`.</span></span> <span data-ttu-id="19fb6-370">Но если вы не управляете типами, как это часто бывает с зависимостями, вы не сможете принудительно реализовать реализацию.</span><span class="sxs-lookup"><span data-stu-id="19fb6-370">But when you don't control the types, as is often the case with dependencies, it's not possible to force an implementation here.</span></span> <span data-ttu-id="19fb6-371">Единственное решение — существенно изменить архитектуру.</span><span class="sxs-lookup"><span data-stu-id="19fb6-371">The only solution is to make large architectural changes.</span></span> <span data-ttu-id="19fb6-372">Граница сериализации также серьезно влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="19fb6-372">The serialization boundary also has serious performance implications.</span></span>

<span data-ttu-id="19fb6-373">Так как у доменов приложений есть такое серьезное ограничение, их сложно реализовать и они работают только в .NET Framework, мы не будем приводить примеры.</span><span class="sxs-lookup"><span data-stu-id="19fb6-373">Because Application Domains have this serious limitation, are complicated to implement, and only work in .NET Framework, we won't give an example of how you might use them here.</span></span> <span data-ttu-id="19fb6-374">Следует знать, что существует такая возможность, но лучше ее не использовать.</span><span class="sxs-lookup"><span data-stu-id="19fb6-374">While they're worth mentioning as a possibility, they're not recommended.</span></span>

<span data-ttu-id="19fb6-375">Если вы хотите попробовать пользовательский домен приложения, см. следующие ссылки.</span><span class="sxs-lookup"><span data-stu-id="19fb6-375">If you're interested in trying to use a custom Application Domain, the following links might help:</span></span>

- [<span data-ttu-id="19fb6-376">Основная документация по доменам приложений</span><span class="sxs-lookup"><span data-stu-id="19fb6-376">Conceptual documentation on Application Domains</span></span>](/dotnet/framework/app-domains/application-domains)
- [<span data-ttu-id="19fb6-377">Примеры использования доменов приложений</span><span class="sxs-lookup"><span data-stu-id="19fb6-377">Examples for using Application Domains</span></span>](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a><span data-ttu-id="19fb6-378">Решения для конфликтов зависимостей, которые не работают в PowerShell</span><span class="sxs-lookup"><span data-stu-id="19fb6-378">Solutions for dependency conflicts that don't work for PowerShell</span></span>

<span data-ttu-id="19fb6-379">Наконец, мы рассмотрим возможности, которые возникают при изучении конфликтов зависимостей .NET. Они могут показаться полезными, но обычно не работают в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-379">Finally, we'll address some possibilities that come up when researching .NET dependency conflicts in .NET that can look promising, but generally won't work for PowerShell.</span></span>

<span data-ttu-id="19fb6-380">Все эти решения представляют собой изменения конфигураций развертывания для среды, в которой вы управляете приложением и, возможно, всем компьютером.</span><span class="sxs-lookup"><span data-stu-id="19fb6-380">These solutions have the common theme that they are changes to deployment configurations for an environment where you control the application and possibly the entire machine.</span></span> <span data-ttu-id="19fb6-381">Эти решения ориентированы на такие сценарии, как веб-серверы и другие приложения, развернутые в серверных средах, где среда предназначена для размещения приложения и может быть настроена пользователем, выполняющим развертывание.</span><span class="sxs-lookup"><span data-stu-id="19fb6-381">These solutions are oriented toward scenarios like web servers and other applications deployed to server environments, where the environment is intended to host the application and is free to be configured by the deploying user.</span></span> <span data-ttu-id="19fb6-382">Они также обычно ориентированы на .NET Framework, то есть не работают с PowerShell 6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="19fb6-382">They also tend to be very much .NET Framework oriented, meaning they do not work with PowerShell 6 or above.</span></span>

<span data-ttu-id="19fb6-383">Если вы уверены, что ваш модуль используется только в средах Windows PowerShell 5.1, которые вы полностью контролируете, некоторые из этих вариантов могут оказаться полезными для вас.</span><span class="sxs-lookup"><span data-stu-id="19fb6-383">If you know that your module is only used in Windows PowerShell 5.1 environments that you have total control over, some of these may be options.</span></span> <span data-ttu-id="19fb6-384">Но, как правило, **модули не должны изменять состояние глобального компьютера таким образом**.</span><span class="sxs-lookup"><span data-stu-id="19fb6-384">In general however, **modules should not modify global machine state like this**.</span></span> <span data-ttu-id="19fb6-385">Это может нарушить конфигурации и привести к проблемам в `powershell.exe`, других модулях или других зависимых приложениях, из-за которых ваш модуль работает непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="19fb6-385">It can break configurations that cause problems in `powershell.exe`, other modules, or other dependent applications that cause your module to fail in unexpected ways.</span></span>

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a><span data-ttu-id="19fb6-386">Перенаправление статической привязки с помощью app.config для принудительного использования одинаковой версии зависимости</span><span class="sxs-lookup"><span data-stu-id="19fb6-386">Static binding redirect with app.config to force using the same dependency version</span></span>

<span data-ttu-id="19fb6-387">Приложения .NET Framework могут использовать преимущества файла `app.config`, чтобы декларативно настроить некоторые реакции приложения на события.</span><span class="sxs-lookup"><span data-stu-id="19fb6-387">.NET Framework applications can take advantage of an `app.config` file to configure some of the application's behaviors declaratively.</span></span> <span data-ttu-id="19fb6-388">Можно создать запись `app.config`, которая настраивает привязку сборки для перенаправления загрузки сборки в определенную версию.</span><span class="sxs-lookup"><span data-stu-id="19fb6-388">It's possible to write an `app.config` entry that configures assembly binding to redirect assembly loading to a particular version.</span></span>

<span data-ttu-id="19fb6-389">В PowerShell у такого сценария есть две проблемы.</span><span class="sxs-lookup"><span data-stu-id="19fb6-389">Two issues with this for PowerShell are:</span></span>

- <span data-ttu-id="19fb6-390">.NET Core не поддерживает `app.config`, поэтому это решение применимо только к `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-390">.NET Core does not support `app.config`, so this solution only applies to `powershell.exe`.</span></span>
- <span data-ttu-id="19fb6-391">`powershell.exe` — это общее приложение, которое находится в каталоге `System32`.</span><span class="sxs-lookup"><span data-stu-id="19fb6-391">`powershell.exe` is a shared application that lives in the `System32` directory.</span></span> <span data-ttu-id="19fb6-392">Скорее всего, ваш модуль не сможет изменить его содержимое во многих системах.</span><span class="sxs-lookup"><span data-stu-id="19fb6-392">It's likely that your module won't be able to modify its contents on many systems.</span></span> <span data-ttu-id="19fb6-393">Даже если это возможно, изменение `app.config` может нарушить существующую конфигурацию или повлиять на загрузку других модулей.</span><span class="sxs-lookup"><span data-stu-id="19fb6-393">Even if it can, modifying the `app.config` could break an existing configuration or affect the loading of other modules.</span></span>

### <a name="setting-codebase-with-appconfig"></a><span data-ttu-id="19fb6-394">Установка `codebase` с помощью app.config</span><span class="sxs-lookup"><span data-stu-id="19fb6-394">Setting `codebase` with app.config</span></span>

<span data-ttu-id="19fb6-395">По тем же причинам попытка настроить параметр `codebase` в `app.config` не будет работать в модулях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19fb6-395">For the same reasons, trying to configure the `codebase` setting in `app.config` is not going to work in PowerShell modules.</span></span>

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a><span data-ttu-id="19fb6-396">Установка зависимостей в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-396">Installing dependencies to the Global Assembly Cache (GAC)</span></span>

<span data-ttu-id="19fb6-397">Еще один способ разрешить конфликты версий зависимостей в .NET Framework — установить зависимости в глобальный кэш сборок, чтобы разные версии можно было загружать из него параллельно.</span><span class="sxs-lookup"><span data-stu-id="19fb6-397">Another way to resolve dependency version conflicts in .NET Framework is to install dependencies to the GAC, so that different versions can be loaded side-by-side from the GAC.</span></span>

<span data-ttu-id="19fb6-398">И снова для модулей PowerShell возникает несколько проблем.</span><span class="sxs-lookup"><span data-stu-id="19fb6-398">Again, for PowerShell modules, the chief issues here are:</span></span>

- <span data-ttu-id="19fb6-399">Глобальный кэш сборок применяется только к .NET Framework, поэтому его нельзя использовать в PowerShell 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="19fb6-399">The GAC only applies to .NET Framework, so this does not help in PowerShell 6 and above.</span></span>
- <span data-ttu-id="19fb6-400">Установка сборок в глобальный кэш сборок — это изменение состояния глобального компьютера, которое может привести к побочным эффектам в других приложениях или других модулях.</span><span class="sxs-lookup"><span data-stu-id="19fb6-400">Installing assemblies to the GAC is a modification of global machine state and may cause side-effects in other applications or to other modules.</span></span> <span data-ttu-id="19fb6-401">Кроме того, это может усложнить работу, даже если ваш модуль имеет необходимые права доступа.</span><span class="sxs-lookup"><span data-stu-id="19fb6-401">It may also be difficult to do correctly, even when your module has the required access privileges.</span></span> <span data-ttu-id="19fb6-402">Если сделать что-то неправильно, могут возникнуть серьезные проблемы на уровне компьютера в других приложениях .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-402">Getting it wrong could cause serious, machine-wide issues in other .NET applications.</span></span>

## <a name="further-reading"></a><span data-ttu-id="19fb6-403">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="19fb6-403">Further reading</span></span>

<span data-ttu-id="19fb6-404">Существует множество статей о конфликтах зависимостей версий сборок .NET.</span><span class="sxs-lookup"><span data-stu-id="19fb6-404">There's plenty more to read on .NET assembly version dependency conflicts.</span></span> <span data-ttu-id="19fb6-405">Рекомендуем начать изучение со следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="19fb6-405">Here are some nice jumping off points:</span></span>

- [<span data-ttu-id="19fb6-406">.NET: сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="19fb6-406">.NET: Assemblies in .NET</span></span>](/dotnet/standard/assembly/)
- [<span data-ttu-id="19fb6-407">.NET Core: алгоритм загрузки управляемых сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-407">.NET Core: The managed assembly loading algorithm</span></span>](/dotnet/core/dependency-loading/loading-managed)
- [<span data-ttu-id="19fb6-408">.NET Core: основные сведения о System.Runtime.Loader.AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="19fb6-408">.NET Core: Understanding System.Runtime.Loader.AssemblyLoadContext</span></span>](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [<span data-ttu-id="19fb6-409">.NET Core: обсуждение решений для параллельной загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-409">.NET Core: Discussion about side-by-side assembly loading solutions</span></span>](https://github.com/dotnet/runtime/issues/13471)
- [<span data-ttu-id="19fb6-410">.NET Framework: перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="19fb6-410">.NET Framework: Redirecting assembly versions</span></span>](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [<span data-ttu-id="19fb6-411">.NET Framework: рекомендации для загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-411">.NET Framework: Best practices for assembly loading</span></span>](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [<span data-ttu-id="19fb6-412">.NET Framework: обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="19fb6-412">.NET Framework: How the runtime locates assemblies</span></span>](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [<span data-ttu-id="19fb6-413">.NET Framework: разрешение загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-413">.NET Framework: Resolve assembly loads</span></span>](/dotnet/standard/assembly/resolve-loads)
- [<span data-ttu-id="19fb6-414">StackOverflow: методы и причины перенаправления привязки сборок</span><span class="sxs-lookup"><span data-stu-id="19fb6-414">StackOverflow: Assembly binding redirect, how and why?</span></span>](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [<span data-ttu-id="19fb6-415">PowerShell: обсуждение реализации AssemblyLoadContexts</span><span class="sxs-lookup"><span data-stu-id="19fb6-415">PowerShell: Discussion about implementing AssemblyLoadContexts</span></span>](https://github.com/PowerShell/PowerShell/issues/11571)
- [<span data-ttu-id="19fb6-416">PowerShell: `Assembly.LoadFile()` не загружается в AssemblyLoadContext по умолчанию</span><span class="sxs-lookup"><span data-stu-id="19fb6-416">PowerShell: `Assembly.LoadFile()` doesn't load into default AssemblyLoadContext</span></span>](https://github.com/PowerShell/PowerShell/issues/12052)
- [<span data-ttu-id="19fb6-417">Рик Штраль (Rick Strahl): "Когда загружается зависимость сборки .NET?"</span><span class="sxs-lookup"><span data-stu-id="19fb6-417">Rick Strahl: When does a .NET assembly dependency get loaded?</span></span>](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [<span data-ttu-id="19fb6-418">Джон Скит (Jon Skeet): "Общие сведения об управлении версиями в .NET"</span><span class="sxs-lookup"><span data-stu-id="19fb6-418">Jon Skeet: Summary of versioning in .NET</span></span>](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [<span data-ttu-id="19fb6-419">Нейт Мак-Мастер (Nate McMaster): "Подробный обзор примитивов .NET Core"</span><span class="sxs-lookup"><span data-stu-id="19fb6-419">Nate McMaster: Deep dive into .NET Core primitives</span></span>](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
