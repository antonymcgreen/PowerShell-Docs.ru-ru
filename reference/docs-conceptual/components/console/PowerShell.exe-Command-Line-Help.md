---
ms.date: 08/14/2018
keywords: powershell,командлет
title: Справка по командной строке PowerShell.exe
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 0a11ebb11d29adf5853c232b3aa10bc72f92bf0c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058519"
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="414cb-103">Справка по командной строке PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="414cb-103">PowerShell.exe Command-Line Help</span></span>

<span data-ttu-id="414cb-104">Вы можете использовать PowerShell.exe для запуска сеанса PowerShell из командной строки другого средства, такого как Cmd.exe, или использовать его в командной строке PowerShell для запуска нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="414cb-104">You can use PowerShell.exe to start a PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the PowerShell command line to start a new session.</span></span> <span data-ttu-id="414cb-105">Используйте указанные параметры для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="414cb-105">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="414cb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="414cb-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="414cb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="414cb-107">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="414cb-108">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="414cb-108">-EncodedCommand <Base64EncodedCommand></span></span>

<span data-ttu-id="414cb-109">Принимает строковую версию команды в кодировке Base 64.</span><span class="sxs-lookup"><span data-stu-id="414cb-109">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="414cb-110">Используйте этот параметр для отправки в PowerShell команд, требующих сложных кавычек или фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="414cb-110">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="414cb-111">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="414cb-111">-ExecutionPolicy <ExecutionPolicy></span></span>

<span data-ttu-id="414cb-112">Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в переменной среды $env:PSExecutionPolicyPreference.</span><span class="sxs-lookup"><span data-stu-id="414cb-112">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="414cb-113">Этот параметр не изменяет политику выполнения PowerShell, заданную в реестре.</span><span class="sxs-lookup"><span data-stu-id="414cb-113">This parameter doesn't change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="414cb-114">Дополнительные сведения о политиках выполнения PowerShell, включая список допустимых значений, см. в статье [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span><span class="sxs-lookup"><span data-stu-id="414cb-114">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="414cb-115">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="414cb-115">-File <FilePath> \[<Parameters>]</span></span>

<span data-ttu-id="414cb-116">Запускает указанный сценарий в локальной области ("с точкой"), чтобы создаваемые сценарием функции и переменные были доступны в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="414cb-116">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="414cb-117">Введите путь к файлу сценария и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="414cb-117">Enter the script file path and any parameters.</span></span> <span data-ttu-id="414cb-118">**File** должен быть последним параметром в команде.</span><span class="sxs-lookup"><span data-stu-id="414cb-118">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="414cb-119">Все значения, введенные после параметра **-File** интерпретируются как путь к файлу скрипта и параметры, передаваемые в него.</span><span class="sxs-lookup"><span data-stu-id="414cb-119">All values typed after the **-File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="414cb-120">Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой).</span><span class="sxs-lookup"><span data-stu-id="414cb-120">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="414cb-121">Например, если в cmd.exe необходимо передать значение переменной среды, вы должны использовать синтаксис cmd.exe `powershell.exe -File .\test.ps1 -TestParam %windir%`.</span><span class="sxs-lookup"><span data-stu-id="414cb-121">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="414cb-122">Напротив, выполнение `powershell.exe -File .\test.ps1 -TestParam $env:windir` в cmd.exe приводит к тому, что скрипт получает строку литералов `$env:windir`, поскольку она не имеет особого значения для текущей оболочки cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="414cb-122">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in cmd.exe results in the script receiving the literal string `$env:windir` because it has no special meaning to the current cmd.exe shell.</span></span>
<span data-ttu-id="414cb-123">Стиль `$env:windir` ссылки на переменную среды _можно_ использовать в параметре `-Command`, так как там он будет интерпретироваться как код PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-123">The `$env:windir` style of environment variable reference _can_ be used inside a `-Command` parameter, since there it will be interpreted as PowerShell code.</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="414cb-124">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="414cb-124">\-InputFormat {Text | XML}</span></span>

<span data-ttu-id="414cb-125">Описывает формат данных, отправляемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-125">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="414cb-126">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="414cb-126">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="414cb-127">-Mta</span><span class="sxs-lookup"><span data-stu-id="414cb-127">-Mta</span></span>

<span data-ttu-id="414cb-128">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="414cb-128">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="414cb-129">Этот параметр впервые появился в PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="414cb-129">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="414cb-130">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="414cb-130">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="414cb-131">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="414cb-131">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="414cb-132">-NoExit</span><span class="sxs-lookup"><span data-stu-id="414cb-132">-NoExit</span></span>

<span data-ttu-id="414cb-133">Не завершает работу после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="414cb-133">Doesn't exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="414cb-134">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="414cb-134">-NoLogo</span></span>

<span data-ttu-id="414cb-135">Скрывает баннер авторских прав при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="414cb-135">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="414cb-136">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="414cb-136">-NonInteractive</span></span>

<span data-ttu-id="414cb-137">Не предоставляет пользователю интерактивный запрос.</span><span class="sxs-lookup"><span data-stu-id="414cb-137">Doesn't present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="414cb-138">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="414cb-138">-NoProfile</span></span>

<span data-ttu-id="414cb-139">Не загружает профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-139">Doesn't load the PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="414cb-140">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="414cb-140">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="414cb-141">Определяет формат выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-141">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="414cb-142">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="414cb-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="414cb-143">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="414cb-143">-PSConsoleFile <FilePath></span></span>

<span data-ttu-id="414cb-144">Загружает указанный файл консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-144">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="414cb-145">Введите путь и имя файла консоли.</span><span class="sxs-lookup"><span data-stu-id="414cb-145">Enter the path and name of the console file.</span></span> <span data-ttu-id="414cb-146">Чтобы создать файл консоли, используйте командлет [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-146">To create a console file, use the [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) cmdlet in PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="414cb-147">-Sta</span><span class="sxs-lookup"><span data-stu-id="414cb-147">-Sta</span></span>

<span data-ttu-id="414cb-148">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="414cb-148">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="414cb-149">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="414cb-149">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="414cb-150">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="414cb-150">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-powershell-version"></a><span data-ttu-id="414cb-151">-Version <PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="414cb-151">-Version <PowerShell Version></span></span>

<span data-ttu-id="414cb-152">Запускает заданную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-152">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="414cb-153">Указанная версия должна быть установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="414cb-153">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="414cb-154">Если на компьютере установлен PowerShell 3.0, допустимыми значениями являются "3.0" и "2.0".</span><span class="sxs-lookup"><span data-stu-id="414cb-154">If PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="414cb-155">По умолчанию используется значение "3.0".</span><span class="sxs-lookup"><span data-stu-id="414cb-155">The default value is "3.0".</span></span>

<span data-ttu-id="414cb-156">Если версия PowerShell 3.0 не установлена, допустимо только значение 2.0.</span><span class="sxs-lookup"><span data-stu-id="414cb-156">If PowerShell 3.0 isn't installed, the only valid value is "2.0".</span></span> <span data-ttu-id="414cb-157">Другие значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="414cb-157">Other values are ignored.</span></span>

<span data-ttu-id="414cb-158">Дополнительные сведения см. в статье [Установка Windows PowerShell](../../setup/installing-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="414cb-158">For more information, see [Installing Windows PowerShell](../../setup/installing-windows-powershell.md).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="414cb-159">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="414cb-159">-WindowStyle <Window style></span></span>

<span data-ttu-id="414cb-160">Задает стиль окна для сеанса.</span><span class="sxs-lookup"><span data-stu-id="414cb-160">Sets the window style for the session.</span></span> <span data-ttu-id="414cb-161">Допустимые значения: Normal, Minimized, Maximized и Hidden.</span><span class="sxs-lookup"><span data-stu-id="414cb-161">Valid values are Normal, Minimized, Maximized, and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="414cb-162">-Command</span><span class="sxs-lookup"><span data-stu-id="414cb-162">-Command</span></span>

<span data-ttu-id="414cb-163">Выполняет указанные команды (с любыми параметрами) как введенные в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-163">Executes the specified commands (with any parameters) as though they were typed at the PowerShell command prompt.</span></span>
<span data-ttu-id="414cb-164">После выполнения PowerShell завершает работу, если не указан параметр **NoExit**.</span><span class="sxs-lookup"><span data-stu-id="414cb-164">After execution, PowerShell exits unless the **NoExit** parameter is specified.</span></span>
<span data-ttu-id="414cb-165">Любой текст после `-Command` отправляется в PowerShell как одна командная строка.</span><span class="sxs-lookup"><span data-stu-id="414cb-165">Any text after `-Command` is sent as a single command line to PowerShell.</span></span>
<span data-ttu-id="414cb-166">Это отличается от того, как `-File` обрабатывает параметры, передаваемые в скрипт.</span><span class="sxs-lookup"><span data-stu-id="414cb-166">This is different from how `-File` handles parameters sent to a script.</span></span>

<span data-ttu-id="414cb-167">Значением `-Command` может быть "–", строка или блок сценария.</span><span class="sxs-lookup"><span data-stu-id="414cb-167">The value of `-Command` can be "-", a string, or a script block.</span></span>
<span data-ttu-id="414cb-168">Результаты команды возвращаются родительской оболочке как десериализованные объекты XML, а не как активные объекты.</span><span class="sxs-lookup"><span data-stu-id="414cb-168">The results of the command are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="414cb-169">Если для `-Command` задано значение "–", текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="414cb-169">If the value of `-Command` is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="414cb-170">Если значением `-Command` является строка, параметр **Command** _должен_ быть указан последним, так как любой знак, введенный после команды, интерпретируется как ее аргумент.</span><span class="sxs-lookup"><span data-stu-id="414cb-170">When the value of `-Command` is a string, **Command** _must_ be the last parameter specified because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="414cb-171">Параметр **Command** выполняет блок сценария только в том случае, когда он может распознать значение, переданное в `-Command` в качестве типа ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="414cb-171">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to `-Command` as a ScriptBlock type.</span></span>
<span data-ttu-id="414cb-172">Это возможно _только_ при запуске PowerShell.exe с другого хоста PowerShell.</span><span class="sxs-lookup"><span data-stu-id="414cb-172">This is _only_ possible when running PowerShell.exe from another PowerShell host.</span></span>
<span data-ttu-id="414cb-173">Существующая переменная может содержать тип ScriptBlock, который возвращается из выражения или анализируется хостом PowerShell как символ блока сценария, заключенный в фигурные скобки `{}`, перед передачей в PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="414cb-173">The ScriptBlock type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to PowerShell.exe.</span></span>

<span data-ttu-id="414cb-174">В cmd.exe отсутствует такая вещь, как блок сценария (или тип ScriptBlock), поэтому значение, передаваемое в параметр **Command**, _всегда_ будет строкой.</span><span class="sxs-lookup"><span data-stu-id="414cb-174">In cmd.exe, there is no such thing as a script block (or ScriptBlock type), so the value passed to **Command** will _always_ be a string.</span></span>
<span data-ttu-id="414cb-175">Вы можете написать блок сценария в строке, но вместо выполнения его поведение будет таким, как если бы вы набирали его в типичном приглашении PowerShell, возвращая содержимое блока сценария обратно.</span><span class="sxs-lookup"><span data-stu-id="414cb-175">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="414cb-176">Строка, переданная в `-Command`, будет по-прежнему выполняться как PowerShell, поэтому фигурные скобки блока сценария редко требуются при запуске из cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="414cb-176">A string passed to `-Command` will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from cmd.exe.</span></span>
<span data-ttu-id="414cb-177">Для выполнения встроенного блока сценария, определенного внутри строки, можно использовать [оператор вызова](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&`.</span><span class="sxs-lookup"><span data-stu-id="414cb-177">To execute an inline script block defined inside a string, the [call operator](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` can be used:</span></span>

```console
"& {<command>}"
```

### <a name="-help---"></a><span data-ttu-id="414cb-178">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="414cb-178">-Help, -?, /?</span></span>

<span data-ttu-id="414cb-179">Показывает синтаксис powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="414cb-179">Shows the syntax of powershell.exe.</span></span> <span data-ttu-id="414cb-180">При вводе команды PowerShell.exe в PowerShell добавляйте в начало параметров команды дефис (-), а не косую черту (/).</span><span class="sxs-lookup"><span data-stu-id="414cb-180">If you are typing a PowerShell.exe command in PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="414cb-181">В Cmd.exe можно использовать как дефис, так и косую черту.</span><span class="sxs-lookup"><span data-stu-id="414cb-181">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="414cb-182">Замечание по устранению неполадок. Обратите внимание, что в PowerShell 2.0 запуск некоторых программ в консоли Windows PowerShell завершается ошибкой с кодом LastExitCode 0xc0000142.</span><span class="sxs-lookup"><span data-stu-id="414cb-182">Troubleshooting Note: In PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="414cb-183">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="414cb-183">EXAMPLES</span></span>

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
