---
ms.date: 05/22/2020
keywords: powershell,командлет
title: Что такое PowerShell?
description: В этой статье представлены общие сведения о среде сценариев PowerShell и ее возможностях.
ms.openlocfilehash: 91fc580af9a3adf43a24c40b4aaf3f1843882705
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500782"
---
# <a name="what-is-powershell"></a><span data-ttu-id="65985-104">Что такое PowerShell?</span><span class="sxs-lookup"><span data-stu-id="65985-104">What is PowerShell?</span></span>

<span data-ttu-id="65985-105">PowerShell — это кроссплатформенная система для автоматизации задач и управления конфигурацией, состоящая из оболочки командной строки и языка сценариев.</span><span class="sxs-lookup"><span data-stu-id="65985-105">PowerShell is a cross-platform task automation and configuration management framework, consisting of a command-line shell and scripting language.</span></span> <span data-ttu-id="65985-106">В отличие от большинства оболочек, которые принимают и возвращают текст, PowerShell построена на основе общеязыковой среды выполнения (CLR) .NET и принимает и возвращает объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="65985-106">Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR), and accepts and returns .NET objects.</span></span> <span data-ttu-id="65985-107">Это фундаментальное отличие, которое подразумевает использование совершенно новых средств и методов автоматизации.</span><span class="sxs-lookup"><span data-stu-id="65985-107">This fundamental change brings entirely new tools and methods for automation.</span></span>

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a><span data-ttu-id="65985-108">Выходные данные являются объектно-ориентированными</span><span class="sxs-lookup"><span data-stu-id="65985-108">Output is object-based</span></span>

<span data-ttu-id="65985-109">В отличие от средств распространенных интерфейсов командной строки командлеты PowerShell предназначены для работы с объектами.</span><span class="sxs-lookup"><span data-stu-id="65985-109">Unlike traditional command-line interfaces, PowerShell cmdlets are designed to deal with objects.</span></span>
<span data-ttu-id="65985-110">Объект — это не просто набор отображаемых на экране символов, а структурированные данные.</span><span class="sxs-lookup"><span data-stu-id="65985-110">An object is structured information that is more than just the string of characters appearing on the screen.</span></span> <span data-ttu-id="65985-111">Выходные данные команды всегда содержат дополнительную информацию, которую при необходимости можно использовать.</span><span class="sxs-lookup"><span data-stu-id="65985-111">Command output always carries extra information that you can use if you need it.</span></span>

<span data-ttu-id="65985-112">Если раньше вы использовали средства обработки текста для работы с данными, вы поймете, что в PowerShell они применяются иначе.</span><span class="sxs-lookup"><span data-stu-id="65985-112">If you've used text-processing tools to process data in the past, you'll find that they behave differently when used in PowerShell.</span></span> <span data-ttu-id="65985-113">В большинстве случаев для получения определенных сведений средства обработки текста не нужны.</span><span class="sxs-lookup"><span data-stu-id="65985-113">In most cases, you don't need text-processing tools to extract specific information.</span></span> <span data-ttu-id="65985-114">Стандартный синтаксис объекта PowerShell позволяет получить прямой доступ к фрагментам данных.</span><span class="sxs-lookup"><span data-stu-id="65985-114">You directly access portions of the data using standard PowerShell object syntax.</span></span>

## <a name="the-command-family-is-extensible"></a><span data-ttu-id="65985-115">Семейство команд является расширяемым</span><span class="sxs-lookup"><span data-stu-id="65985-115">The command family is extensible</span></span>

<span data-ttu-id="65985-116">Такие интерфейсы, как `cmd.exe`, не позволяют расширять набор встроенных команд напрямую.</span><span class="sxs-lookup"><span data-stu-id="65985-116">Interfaces such as `cmd.exe` don't provide a way for you to directly extend the built-in command set.</span></span> <span data-ttu-id="65985-117">Вы можете создавать внешние программы командной строки, выполняемые в `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="65985-117">You can create external command-line tools that run in `cmd.exe`.</span></span> <span data-ttu-id="65985-118">Но у этих внешних программ нет служб, таких как интеграция справки.</span><span class="sxs-lookup"><span data-stu-id="65985-118">But these external tools don't have services, such as Help integration.</span></span> <span data-ttu-id="65985-119">Интерфейс `cmd.exe` не будет автоматически знать, что эти внешние программы являются действительными командами.</span><span class="sxs-lookup"><span data-stu-id="65985-119">`cmd.exe` doesn't automatically know that these external tools are valid commands.</span></span>

<span data-ttu-id="65985-120">Команды в PowerShell называются _командлетами_ .</span><span class="sxs-lookup"><span data-stu-id="65985-120">The commands in PowerShell are known as _cmdlets_ .</span></span> <span data-ttu-id="65985-121">Каждый командлет можно применять отдельно, но наиболее эффективным является их совместное использование для выполнения сложных задач.</span><span class="sxs-lookup"><span data-stu-id="65985-121">You can use each cmdlet separately, but their power is realized when you combine them to perform complex tasks.</span></span> <span data-ttu-id="65985-122">Как и многие другие оболочки, PowerShell предоставляет доступ к файловой системе на компьютере.</span><span class="sxs-lookup"><span data-stu-id="65985-122">Like many shells, PowerShell gives you access to the file system on the computer.</span></span> <span data-ttu-id="65985-123">_Поставщики_ PowerShell позволяют обращаться к другим хранилищам данных, например к реестру и хранилищам сертификатов, так же легко, как и к файловой системе.</span><span class="sxs-lookup"><span data-stu-id="65985-123">PowerShell _providers_ enable you to access other data stores, such as the registry and the certificate stores, as easily as you access the file system.</span></span>

<span data-ttu-id="65985-124">Вы можете создавать собственные командлеты и модули функций, используя сценарии или скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="65985-124">You can create your own cmdlet and function modules using compiled code or scripts.</span></span> <span data-ttu-id="65985-125">Модули могут добавлять командлеты и поставщики в оболочку.</span><span class="sxs-lookup"><span data-stu-id="65985-125">Modules can add cmdlets and providers to the shell.</span></span> <span data-ttu-id="65985-126">PowerShell также поддерживает сценарии, аналогичные сценариям оболочки UNIX и пакетным файлам `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="65985-126">PowerShell also supports scripts that are analogous to UNIX shell scripts and `cmd.exe` batch files.</span></span>

## <a name="support-for-command-aliases"></a><span data-ttu-id="65985-127">Поддержка псевдонимов команд.</span><span class="sxs-lookup"><span data-stu-id="65985-127">Support for command aliases</span></span>

<span data-ttu-id="65985-128">PowerShell поддерживает псевдонимы для вызова команд с помощью альтернативных имен.</span><span class="sxs-lookup"><span data-stu-id="65985-128">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="65985-129">Благодаря наличию псевдонимов пользователи с опытом работы с другими оболочками могут использовать уже известные им распространенные имена команд для выполнения схожих операций в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65985-129">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="65985-130">Механизм псевдонимов заключается в связывании нового имени с определенной командой.</span><span class="sxs-lookup"><span data-stu-id="65985-130">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="65985-131">Например, в PowerShell есть внутренняя функция с именем `Clear-Host`, которая очищает командное окно.</span><span class="sxs-lookup"><span data-stu-id="65985-131">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="65985-132">Вы можете ввести в командной строке псевдоним `cls` или `clear`.</span><span class="sxs-lookup"><span data-stu-id="65985-132">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="65985-133">PowerShell интерпретирует эти псевдонимы и запускает функцию `Clear-Host`.</span><span class="sxs-lookup"><span data-stu-id="65985-133">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="65985-134">Это помогает пользователям изучать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65985-134">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="65985-135">Большинство пользователей `cmd.exe` и Unix применяют большой репертуар команд, которые они уже помнят наизусть.</span><span class="sxs-lookup"><span data-stu-id="65985-135">First, most `cmd.exe` and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="65985-136">Их эквиваленты в PowerShell могут возвращать отличающиеся результаты.</span><span class="sxs-lookup"><span data-stu-id="65985-136">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="65985-137">Но эти результаты достаточно схожи, чтобы пользователи могли работать, не зная имя соответствующей команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65985-137">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="65985-138">Другой трудностью при освоении новой командной оболочки является "мышечная память".</span><span class="sxs-lookup"><span data-stu-id="65985-138">"Muscle memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="65985-139">Если вы много лет использовали `cmd.exe`, вы можете по привычке ввести команду `cls` для очистки экрана.</span><span class="sxs-lookup"><span data-stu-id="65985-139">If you have used `cmd.exe` for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="65985-140">Если псевдоним для `Clear-Host` не настроен, вы получите сообщение об ошибке и не будете знать, как очистить экран.</span><span class="sxs-lookup"><span data-stu-id="65985-140">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

## <a name="powershell-handles-console-input-and-display"></a><span data-ttu-id="65985-141">PowerShell обрабатывает ввод и отображение данных в консоли</span><span class="sxs-lookup"><span data-stu-id="65985-141">PowerShell handles console input and display</span></span>

<span data-ttu-id="65985-142">Когда вы вводите команду, PowerShell всегда обрабатывает входные данные командной строки напрямую.</span><span class="sxs-lookup"><span data-stu-id="65985-142">When you type a command, PowerShell always processes the command-line input directly.</span></span> <span data-ttu-id="65985-143">PowerShell также форматирует выходные данные, отображаемые на экране.</span><span class="sxs-lookup"><span data-stu-id="65985-143">PowerShell also formats the output that you see on the screen.</span></span> <span data-ttu-id="65985-144">Это важно, так как нагрузка, требуемая для обработки каждого командлета, сокращается,</span><span class="sxs-lookup"><span data-stu-id="65985-144">This difference is significant because it reduces the work required of each cmdlet.</span></span> <span data-ttu-id="65985-145">и действия выполняются аналогичным образом независимо от используемого командлета.</span><span class="sxs-lookup"><span data-stu-id="65985-145">It ensures that you can always do things the same way with any cmdlet.</span></span> <span data-ttu-id="65985-146">Разработчикам командлетов не нужно писать код для синтаксического анализа аргументов командной строки или форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="65985-146">Cmdlet developers don't need to write code to parse the command-line arguments or format the output.</span></span>

<span data-ttu-id="65985-147">Традиционные программы командной строки используют собственные схемы для запроса и отображения справки.</span><span class="sxs-lookup"><span data-stu-id="65985-147">Traditional command-line tools have their own schemes for requesting and displaying Help.</span></span> <span data-ttu-id="65985-148">Некоторые программы командной строки используют `/?` для показа справки, а другие используют `-?`, `/H` или даже `//`.</span><span class="sxs-lookup"><span data-stu-id="65985-148">Some command-line tools use `/?` to trigger the Help display; others use `-?`, `/H`, or even `//`.</span></span> <span data-ttu-id="65985-149">Некоторые отображают справку в окне графического пользовательского интерфейса, а не в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="65985-149">Some will display Help in a GUI window, rather than in the console display.</span></span> <span data-ttu-id="65985-150">Если введен неправильный параметр, средство может проигнорировать ошибку и автоматически начать выполнение задачи.</span><span class="sxs-lookup"><span data-stu-id="65985-150">If you use the wrong parameter, the tool might ignore what you typed and begin executing a task automatically.</span></span>
<span data-ttu-id="65985-151">Поскольку PowerShell автоматически анализирует и обрабатывает командную строку, параметр `-?` всегда означает "показать справку по этой команде".</span><span class="sxs-lookup"><span data-stu-id="65985-151">Since PowerShell automatically parses and processes the command line, the `-?` parameter always means "show me Help for this command".</span></span>

> [!NOTE]
> <span data-ttu-id="65985-152">Когда вы запускаете в PowerShell графическое приложение, для него открывается окно.</span><span class="sxs-lookup"><span data-stu-id="65985-152">If you run a graphic application in PowerShell, the window for the application opens.</span></span>
> <span data-ttu-id="65985-153">PowerShell вмешивается в процесс только при обработке заданных вами в командной строке входных данных или при возврате выходных данных приложения в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="65985-153">PowerShell intervenes only when processing the command-line input you supply or the application output returned to the console window.</span></span> <span data-ttu-id="65985-154">На внутреннюю работу приложения система не влияет.</span><span class="sxs-lookup"><span data-stu-id="65985-154">It does not affect how the application works internally.</span></span>

## <a name="powershell-has-a-pipeline"></a><span data-ttu-id="65985-155">PowerShell включает конвейер</span><span class="sxs-lookup"><span data-stu-id="65985-155">PowerShell has a pipeline</span></span>

<span data-ttu-id="65985-156">Пожалуй, конвейеры являются наиболее полезной концепцией в интерфейсах командной строки.</span><span class="sxs-lookup"><span data-stu-id="65985-156">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="65985-157">При правильном использовании конвейеры упрощают работу со сложными командами и отслеживание потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="65985-157">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work.</span></span> <span data-ttu-id="65985-158">Каждая команда в конвейере передает свои выходные данные, элемент за элементом, следующей команде.</span><span class="sxs-lookup"><span data-stu-id="65985-158">Each command in a pipeline passes its output, item by item, to the next command.</span></span> <span data-ttu-id="65985-159">Команды обрабатывают только один объект за раз.</span><span class="sxs-lookup"><span data-stu-id="65985-159">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="65985-160">Это снижает потребление ресурсов и позволяет получать выходные данные немедленно.</span><span class="sxs-lookup"><span data-stu-id="65985-160">The result is reduced resource consumption and the ability to get output immediately.</span></span>

<span data-ttu-id="65985-161">Эта нотация конвейера похожа на нотацию, которая используется в других оболочках.</span><span class="sxs-lookup"><span data-stu-id="65985-161">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="65985-162">На первый взгляд не совсем понятно, чем отличаются конвейеры в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65985-162">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="65985-163">Хотя вы видите на экране текст, PowerShell передает по конвейеру между командами не текст, а объекты.</span><span class="sxs-lookup"><span data-stu-id="65985-163">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

<span data-ttu-id="65985-164">Например, вы можете использовать командлет `Out-Host` для принудительного постраничного отображения выходных данных из другой команды. На экране эти данные будут показаны как обычный текст, разбитый на страницы:</span><span class="sxs-lookup"><span data-stu-id="65985-164">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="65985-165">Разбиение на страницы также снижает потребление ресурсов ЦП, так обработку продолжает командлет `Out-Host`, когда он получает всю страницу для отображения.</span><span class="sxs-lookup"><span data-stu-id="65985-165">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="65985-166">Командлет, стоящий в конвейере выше, приостанавливает выполнение, пока не будет готова следующая страница выходных данных.</span><span class="sxs-lookup"><span data-stu-id="65985-166">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

### <a name="objects-in-the-pipeline"></a><span data-ttu-id="65985-167">Объекты в конвейере</span><span class="sxs-lookup"><span data-stu-id="65985-167">Objects in the pipeline</span></span>

<span data-ttu-id="65985-168">При запуске командлета в PowerShell вы видите выходные данные в виде текста — именно так в окне консоли и должны отображаться объекты.</span><span class="sxs-lookup"><span data-stu-id="65985-168">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="65985-169">В текстовом представлении могут отображаться не все свойства выводимого объекта.</span><span class="sxs-lookup"><span data-stu-id="65985-169">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="65985-170">Например, рассмотрим командлет `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="65985-170">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="65985-171">Эти выходные данные в виде текста содержат сводную информацию, а не полное представление объекта, возвращаемого командлетом `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="65985-171">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="65985-172">Процесс, который форматирует данные для отображения на экране, добавляет к выходным данным заголовок.</span><span class="sxs-lookup"><span data-stu-id="65985-172">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

```powershell
Get-Location
```

```Output
Path
----
C:\
```

<span data-ttu-id="65985-173">При передаче выходных данных по конвейеру в командлет `Get-Member` отображаются сведения об объекте, возвращаемом `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="65985-173">Piping the output to the `Get-Member` cmdlet displays information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="65985-174">Командлет `Get-Location` возвращает объект **PathInfo** , который содержит текущий путь и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="65985-174">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>

## <a name="built-in-help-system"></a><span data-ttu-id="65985-175">Встроенная система справки</span><span class="sxs-lookup"><span data-stu-id="65985-175">Built-in help system</span></span>

<span data-ttu-id="65985-176">PowerShell включает подробные справочные статьи, подобные `man`-страницам Unix, которые поясняют понятия PowerShell и синтаксис команд.</span><span class="sxs-lookup"><span data-stu-id="65985-176">Similar to Unix `man` pages, PowerShell includes detailed help articles that explain PowerShell concepts and command syntax.</span></span> <span data-ttu-id="65985-177">Эти статьи можно отобразить в командной строке с помощью командлета [Get-Help][] или открыть в актуальной версии документации PowerShell в Интернете.</span><span class="sxs-lookup"><span data-stu-id="65985-177">Use the [Get-Help][] cmdlet to display these articles at the command prompt or view the most recently updated versions of these articles in the PowerShell documentation online.</span></span>

## <a name="next-steps"></a><span data-ttu-id="65985-178">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="65985-178">Next steps</span></span>

<span data-ttu-id="65985-179">Дополнительные сведения о PowerShell см. в разделе **Изучение PowerShell** этого сайта.</span><span class="sxs-lookup"><span data-stu-id="65985-179">To learn more about PowerShell, see the **Learning PowerShell** section of this site.</span></span>

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help
