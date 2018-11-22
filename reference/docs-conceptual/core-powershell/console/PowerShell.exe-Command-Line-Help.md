---
ms.date: 08/14/2018
keywords: powershell,командлет
title: Справка по командной строке PowerShell.exe
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 0a11ebb11d29adf5853c232b3aa10bc72f92bf0c
ms.sourcegitcommit: 03c7672ee72698fe88a73e99702ceaadf87e702f
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51691836"
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="25eb3-103">Справка по командной строке PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="25eb3-103">PowerShell.exe Command-Line Help</span></span>

<span data-ttu-id="25eb3-104">Вы можете использовать PowerShell.exe для запуска сеанса PowerShell из командной строки другого средства, такого как Cmd.exe, или использовать его в командной строке PowerShell для запуска нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="25eb3-104">You can use PowerShell.exe to start a PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the PowerShell command line to start a new session.</span></span> <span data-ttu-id="25eb3-105">Используйте указанные параметры для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="25eb3-105">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="25eb3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25eb3-106">Syntax</span></span>

```syntax
PowerShell[.exe]
       [-Command { - | <script-block> [-args <arg-array>]
                     | <string> [<CommandParameters>] } ]
       [-EncodedCommand <Base64EncodedCommand>]
       [-ExecutionPolicy <ExecutionPolicy>]
       [-File <FilePath> [<Args>]]
       [-InputFormat {Text | XML}]
       [-Mta]
       [-NoExit]
       [-NoLogo]
       [-NonInteractive]
       [-NoProfile]
       [-OutputFormat {Text | XML}]
       [-PSConsoleFile <FilePath> | -Version <PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="25eb3-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="25eb3-107">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="25eb3-108">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="25eb3-108">-EncodedCommand <Base64EncodedCommand></span></span>

<span data-ttu-id="25eb3-109">Принимает строковую версию команды в кодировке Base 64.</span><span class="sxs-lookup"><span data-stu-id="25eb3-109">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="25eb3-110">Используйте этот параметр для отправки в PowerShell команд, требующих сложных кавычек или фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="25eb3-110">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="25eb3-111">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="25eb3-111">-ExecutionPolicy <ExecutionPolicy></span></span>

<span data-ttu-id="25eb3-112">Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в переменной среды $env:PSExecutionPolicyPreference.</span><span class="sxs-lookup"><span data-stu-id="25eb3-112">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="25eb3-113">Этот параметр не изменяет политику выполнения PowerShell, заданную в реестре.</span><span class="sxs-lookup"><span data-stu-id="25eb3-113">This parameter doesn't change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="25eb3-114">Дополнительные сведения о политиках выполнения PowerShell, включая список допустимых значений, см. в статье [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span><span class="sxs-lookup"><span data-stu-id="25eb3-114">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="25eb3-115">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="25eb3-115">-File <FilePath> \[<Parameters>]</span></span>

<span data-ttu-id="25eb3-116">Запускает указанный сценарий в локальной области ("с точкой"), чтобы создаваемые сценарием функции и переменные были доступны в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="25eb3-116">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="25eb3-117">Введите путь к файлу сценария и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="25eb3-117">Enter the script file path and any parameters.</span></span> <span data-ttu-id="25eb3-118">**File** должен быть последним параметром в команде.</span><span class="sxs-lookup"><span data-stu-id="25eb3-118">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="25eb3-119">Все значения, введенные после параметра **-File** интерпретируются как путь к файлу скрипта и параметры, передаваемые в него.</span><span class="sxs-lookup"><span data-stu-id="25eb3-119">All values typed after the **-File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="25eb3-120">Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой).</span><span class="sxs-lookup"><span data-stu-id="25eb3-120">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="25eb3-121">Например если вы находитесь в cmd.exe и хотите передать значение переменной среды, используется синтаксис cmd.exe: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="25eb3-121">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="25eb3-122">Напротив, запускать `powershell.exe -File .\test.ps1 -TestParam $env:windir` в результатах cmd.exe в скрипте, получение строковый литерал `$env:windir` , так как он не имеет специального значения в текущей оболочке cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="25eb3-122">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in cmd.exe results in the script receiving the literal string `$env:windir` because it has no special meaning to the current cmd.exe shell.</span></span>
<span data-ttu-id="25eb3-123">`$env:windir` Стиль ссылка на переменную среды _можно_ использоваться внутри `-Command` параметра, так как существует будут интерпретироваться как код PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-123">The `$env:windir` style of environment variable reference _can_ be used inside a `-Command` parameter, since there it will be interpreted as PowerShell code.</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="25eb3-124">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="25eb3-124">\-InputFormat {Text | XML}</span></span>

<span data-ttu-id="25eb3-125">Описывает формат данных, отправляемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-125">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="25eb3-126">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="25eb3-126">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="25eb3-127">-Mta</span><span class="sxs-lookup"><span data-stu-id="25eb3-127">-Mta</span></span>

<span data-ttu-id="25eb3-128">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="25eb3-128">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="25eb3-129">Этот параметр впервые появился в PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="25eb3-129">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="25eb3-130">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="25eb3-130">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="25eb3-131">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="25eb3-131">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="25eb3-132">-NoExit</span><span class="sxs-lookup"><span data-stu-id="25eb3-132">-NoExit</span></span>

<span data-ttu-id="25eb3-133">Не завершает работу после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="25eb3-133">Doesn't exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="25eb3-134">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="25eb3-134">-NoLogo</span></span>

<span data-ttu-id="25eb3-135">Скрывает баннер авторских прав при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="25eb3-135">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="25eb3-136">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="25eb3-136">-NonInteractive</span></span>

<span data-ttu-id="25eb3-137">Не предоставляет пользователю интерактивный запрос.</span><span class="sxs-lookup"><span data-stu-id="25eb3-137">Doesn't present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="25eb3-138">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="25eb3-138">-NoProfile</span></span>

<span data-ttu-id="25eb3-139">Не загружает профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-139">Doesn't load the PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="25eb3-140">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="25eb3-140">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="25eb3-141">Определяет формат выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-141">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="25eb3-142">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="25eb3-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="25eb3-143">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="25eb3-143">-PSConsoleFile <FilePath></span></span>

<span data-ttu-id="25eb3-144">Загружает указанный файл консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-144">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="25eb3-145">Введите путь и имя файла консоли.</span><span class="sxs-lookup"><span data-stu-id="25eb3-145">Enter the path and name of the console file.</span></span> <span data-ttu-id="25eb3-146">Чтобы создать файл консоли, используйте командлет [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-146">To create a console file, use the [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) cmdlet in PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="25eb3-147">-Sta</span><span class="sxs-lookup"><span data-stu-id="25eb3-147">-Sta</span></span>

<span data-ttu-id="25eb3-148">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="25eb3-148">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="25eb3-149">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="25eb3-149">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="25eb3-150">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="25eb3-150">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-powershell-version"></a><span data-ttu-id="25eb3-151">-Version <PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="25eb3-151">-Version <PowerShell Version></span></span>

<span data-ttu-id="25eb3-152">Запускает заданную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-152">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="25eb3-153">Указанная версия должна быть установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="25eb3-153">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="25eb3-154">Если на компьютере установлен PowerShell 3.0, допустимыми значениями являются "3.0" и "2.0".</span><span class="sxs-lookup"><span data-stu-id="25eb3-154">If PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="25eb3-155">По умолчанию используется значение "3.0".</span><span class="sxs-lookup"><span data-stu-id="25eb3-155">The default value is "3.0".</span></span>

<span data-ttu-id="25eb3-156">Если версия PowerShell 3.0 не установлена, допустимо только значение 2.0.</span><span class="sxs-lookup"><span data-stu-id="25eb3-156">If PowerShell 3.0 isn't installed, the only valid value is "2.0".</span></span> <span data-ttu-id="25eb3-157">Другие значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="25eb3-157">Other values are ignored.</span></span>

<span data-ttu-id="25eb3-158">Дополнительные сведения см. в статье [Установка Windows PowerShell](../../setup/installing-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="25eb3-158">For more information, see [Installing Windows PowerShell](../../setup/installing-windows-powershell.md).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="25eb3-159">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="25eb3-159">-WindowStyle <Window style></span></span>

<span data-ttu-id="25eb3-160">Задает стиль окна для сеанса.</span><span class="sxs-lookup"><span data-stu-id="25eb3-160">Sets the window style for the session.</span></span> <span data-ttu-id="25eb3-161">Допустимые значения: Normal, Minimized, Maximized и Hidden.</span><span class="sxs-lookup"><span data-stu-id="25eb3-161">Valid values are Normal, Minimized, Maximized, and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="25eb3-162">-Command</span><span class="sxs-lookup"><span data-stu-id="25eb3-162">-Command</span></span>

<span data-ttu-id="25eb3-163">Выполняет указанные команды (с любыми параметрами) как введенные в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-163">Executes the specified commands (with any parameters) as though they were typed at the PowerShell command prompt.</span></span>
<span data-ttu-id="25eb3-164">После выполнения PowerShell завершает работу, если не **NoExit** указан параметр.</span><span class="sxs-lookup"><span data-stu-id="25eb3-164">After execution, PowerShell exits unless the **NoExit** parameter is specified.</span></span>
<span data-ttu-id="25eb3-165">Любой текст после `-Command` отправляется в PowerShell как одна командная строка.</span><span class="sxs-lookup"><span data-stu-id="25eb3-165">Any text after `-Command` is sent as a single command line to PowerShell.</span></span>
<span data-ttu-id="25eb3-166">Это отличается от того, как `-File` обрабатывает параметры, передаваемые в скрипт.</span><span class="sxs-lookup"><span data-stu-id="25eb3-166">This is different from how `-File` handles parameters sent to a script.</span></span>

<span data-ttu-id="25eb3-167">Значение `-Command` может быть «-», строка или блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="25eb3-167">The value of `-Command` can be "-", a string, or a script block.</span></span>
<span data-ttu-id="25eb3-168">Результаты выполнения команды возвращаются родительской оболочке как десериализованные объекты XML, а не как активные объекты.</span><span class="sxs-lookup"><span data-stu-id="25eb3-168">The results of the command are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="25eb3-169">Если значение `-Command` — «-», текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="25eb3-169">If the value of `-Command` is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="25eb3-170">Когда значение `-Command` представляет собой строку, **команда** _необходимо_ быть последним параметром, так как любой знак, введенный после команды, интерпретируется как ее аргумент.</span><span class="sxs-lookup"><span data-stu-id="25eb3-170">When the value of `-Command` is a string, **Command** _must_ be the last parameter specified because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="25eb3-171">**Команда** параметр принимает только блок скрипта для выполнения при его может распознать значение, передаваемое `-Command` как тип блок сценария.</span><span class="sxs-lookup"><span data-stu-id="25eb3-171">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to `-Command` as a ScriptBlock type.</span></span>
<span data-ttu-id="25eb3-172">Это _только_ возможно при использовании PowerShell.exe с другого узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25eb3-172">This is _only_ possible when running PowerShell.exe from another PowerShell host.</span></span>
<span data-ttu-id="25eb3-173">Тип может содержаться в существующей переменной, возвращаемый из выражения или проанализированный с PowerShell блок сценария размещения как блок скрипта литерала, заключенных в фигурные скобки `{}`, перед передачей в PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="25eb3-173">The ScriptBlock type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to PowerShell.exe.</span></span>

<span data-ttu-id="25eb3-174">В cmd.exe, нет такого понятия, как блок скрипта (или тип блок сценария), поэтому значение, передаваемое **команда** будет _всегда_ быть строкой.</span><span class="sxs-lookup"><span data-stu-id="25eb3-174">In cmd.exe, there is no such thing as a script block (or ScriptBlock type), so the value passed to **Command** will _always_ be a string.</span></span>
<span data-ttu-id="25eb3-175">Можно написать блок скрипта внутри строки, но вместо выполнения он будет вести себя точно так, будто бы он был введен в обычной командной строке PowerShell, выводя содержимое скрипта заблокировать обратно вам.</span><span class="sxs-lookup"><span data-stu-id="25eb3-175">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="25eb3-176">Строка, передаваемая в `-Command` по-прежнему будет выполняться как PowerShell, чтобы фигурные скобки блок скрипта часто не являются обязательными в первую очередь при запуске из cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="25eb3-176">A string passed to `-Command` will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from cmd.exe.</span></span>
<span data-ttu-id="25eb3-177">Для выполнения встроенного блока скрипта, определенные внутри строки, [оператор вызова](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` можно использовать:</span><span class="sxs-lookup"><span data-stu-id="25eb3-177">To execute an inline script block defined inside a string, the [call operator](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` can be used:</span></span>

```console
"& {<command>}"
```

### <a name="-help---"></a><span data-ttu-id="25eb3-178">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="25eb3-178">-Help, -?, /?</span></span>

<span data-ttu-id="25eb3-179">Показывает синтаксис powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="25eb3-179">Shows the syntax of powershell.exe.</span></span> <span data-ttu-id="25eb3-180">При вводе команды PowerShell.exe в PowerShell добавляйте в начало параметров команды дефис (-), а не косую черту (/).</span><span class="sxs-lookup"><span data-stu-id="25eb3-180">If you are typing a PowerShell.exe command in PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="25eb3-181">В Cmd.exe можно использовать как дефис, так и косую черту.</span><span class="sxs-lookup"><span data-stu-id="25eb3-181">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="25eb3-182">Замечание по устранению неполадок. Обратите внимание, что в PowerShell 2.0 запуск некоторых программ в консоли Windows PowerShell завершается ошибкой с кодом LastExitCode 0xc0000142.</span><span class="sxs-lookup"><span data-stu-id="25eb3-182">Troubleshooting Note: In PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="25eb3-183">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="25eb3-183">EXAMPLES</span></span>

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
