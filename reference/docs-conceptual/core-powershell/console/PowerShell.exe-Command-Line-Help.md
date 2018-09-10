---
ms.date: 08/14/2018
keywords: powershell,командлет
title: Справка по командной строке PowerShell.exe
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: c7f35511e876e8e5189d8a2b949555603d43f731
ms.sourcegitcommit: 56b9be8503a5a1342c0b85b36f5ba6f57c281b63
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "43133097"
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="82abe-103">Справка по командной строке PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="82abe-103">PowerShell.exe Command-Line Help</span></span>

<span data-ttu-id="82abe-104">Вы можете использовать PowerShell.exe для запуска сеанса PowerShell из командной строки другого средства, такого как Cmd.exe, или использовать его в командной строке PowerShell для запуска нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="82abe-104">You can use PowerShell.exe to start a PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the PowerShell command line to start a new session.</span></span> <span data-ttu-id="82abe-105">Используйте указанные параметры для настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="82abe-105">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="82abe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82abe-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="82abe-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="82abe-107">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="82abe-108">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="82abe-108">-EncodedCommand <Base64EncodedCommand></span></span>

<span data-ttu-id="82abe-109">Принимает строковую версию команды в кодировке Base 64.</span><span class="sxs-lookup"><span data-stu-id="82abe-109">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="82abe-110">Используйте этот параметр для отправки в PowerShell команд, требующих сложных кавычек или фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="82abe-110">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="82abe-111">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="82abe-111">-ExecutionPolicy <ExecutionPolicy></span></span>

<span data-ttu-id="82abe-112">Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в переменной среды $env:PSExecutionPolicyPreference.</span><span class="sxs-lookup"><span data-stu-id="82abe-112">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="82abe-113">Этот параметр не изменяет политику выполнения PowerShell, заданную в реестре.</span><span class="sxs-lookup"><span data-stu-id="82abe-113">This parameter doesn't change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="82abe-114">Дополнительные сведения о политиках выполнения PowerShell, включая список допустимых значений, см. в статье [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span><span class="sxs-lookup"><span data-stu-id="82abe-114">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="82abe-115">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="82abe-115">-File <FilePath> \[<Parameters>]</span></span>

<span data-ttu-id="82abe-116">Запускает указанный сценарий в локальной области ("с точкой"), чтобы создаваемые сценарием функции и переменные были доступны в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="82abe-116">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="82abe-117">Введите путь к файлу сценария и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="82abe-117">Enter the script file path and any parameters.</span></span> <span data-ttu-id="82abe-118">**File** должен быть последним параметром в команде.</span><span class="sxs-lookup"><span data-stu-id="82abe-118">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="82abe-119">Все значения, введенные после параметра **-File** интерпретируются как путь к файлу скрипта и параметры, передаваемые в него.</span><span class="sxs-lookup"><span data-stu-id="82abe-119">All values typed after the **-File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="82abe-120">Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой).</span><span class="sxs-lookup"><span data-stu-id="82abe-120">Parameters passed to the script are passed as literal strings (after interpretation by the current shell).</span></span> <span data-ttu-id="82abe-121">Например, если вы находитесь в файле cmd.exe и хотите передать значение переменной среды, используйте синтаксис cmd.exe: `powershell -File .\test.ps1 -Sample %windir%`. В этом примере скрипт получит строковый литерал `$env:windir`, а не значение этой переменной среды: `powershell -File .\test.ps1 -Sample $env:windir`.</span><span class="sxs-lookup"><span data-stu-id="82abe-121">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell -File .\test.ps1 -Sample %windir%` In this example, the script receives the literal string `$env:windir` and not the value of that environmental variable: `powershell -File .\test.ps1 -Sample $env:windir`</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="82abe-122">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="82abe-122">\-InputFormat {Text | XML}</span></span>

<span data-ttu-id="82abe-123">Описывает формат данных, отправляемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-123">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="82abe-124">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="82abe-124">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="82abe-125">-Mta</span><span class="sxs-lookup"><span data-stu-id="82abe-125">-Mta</span></span>

<span data-ttu-id="82abe-126">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="82abe-126">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="82abe-127">Этот параметр впервые появился в PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="82abe-127">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="82abe-128">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="82abe-128">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="82abe-129">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="82abe-129">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="82abe-130">-NoExit</span><span class="sxs-lookup"><span data-stu-id="82abe-130">-NoExit</span></span>

<span data-ttu-id="82abe-131">Не завершает работу после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="82abe-131">Doesn't exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="82abe-132">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="82abe-132">-NoLogo</span></span>

<span data-ttu-id="82abe-133">Скрывает баннер авторских прав при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="82abe-133">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="82abe-134">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="82abe-134">-NonInteractive</span></span>

<span data-ttu-id="82abe-135">Не предоставляет пользователю интерактивный запрос.</span><span class="sxs-lookup"><span data-stu-id="82abe-135">Doesn't present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="82abe-136">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="82abe-136">-NoProfile</span></span>

<span data-ttu-id="82abe-137">Не загружает профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-137">Doesn't load the PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="82abe-138">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="82abe-138">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="82abe-139">Определяет формат выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-139">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="82abe-140">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="82abe-140">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="82abe-141">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="82abe-141">-PSConsoleFile <FilePath></span></span>

<span data-ttu-id="82abe-142">Загружает указанный файл консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-142">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="82abe-143">Введите путь и имя файла консоли.</span><span class="sxs-lookup"><span data-stu-id="82abe-143">Enter the path and name of the console file.</span></span> <span data-ttu-id="82abe-144">Чтобы создать файл консоли, используйте командлет [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-144">To create a console file, use the [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) cmdlet in PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="82abe-145">-Sta</span><span class="sxs-lookup"><span data-stu-id="82abe-145">-Sta</span></span>

<span data-ttu-id="82abe-146">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="82abe-146">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="82abe-147">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="82abe-147">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="82abe-148">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="82abe-148">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-powershell-version"></a><span data-ttu-id="82abe-149">-Version <PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="82abe-149">-Version <PowerShell Version></span></span>

<span data-ttu-id="82abe-150">Запускает заданную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-150">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="82abe-151">Указанная версия должна быть установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="82abe-151">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="82abe-152">Если на компьютере установлен PowerShell 3.0, допустимыми значениями являются "3.0" и "2.0".</span><span class="sxs-lookup"><span data-stu-id="82abe-152">If PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="82abe-153">По умолчанию используется значение "3.0".</span><span class="sxs-lookup"><span data-stu-id="82abe-153">The default value is "3.0".</span></span>

<span data-ttu-id="82abe-154">Если версия PowerShell 3.0 не установлена, допустимо только значение 2.0.</span><span class="sxs-lookup"><span data-stu-id="82abe-154">If PowerShell 3.0 isn't installed, the only valid value is "2.0".</span></span> <span data-ttu-id="82abe-155">Другие значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="82abe-155">Other values are ignored.</span></span>

<span data-ttu-id="82abe-156">Дополнительные сведения см. в статье [Установка Windows PowerShell](../../setup/installing-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="82abe-156">For more information, see [Installing Windows PowerShell](../../setup/installing-windows-powershell.md).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="82abe-157">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="82abe-157">-WindowStyle <Window style></span></span>

<span data-ttu-id="82abe-158">Задает стиль окна для сеанса.</span><span class="sxs-lookup"><span data-stu-id="82abe-158">Sets the window style for the session.</span></span> <span data-ttu-id="82abe-159">Допустимые значения: Normal, Minimized, Maximized и Hidden.</span><span class="sxs-lookup"><span data-stu-id="82abe-159">Valid values are Normal, Minimized, Maximized, and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="82abe-160">-Command</span><span class="sxs-lookup"><span data-stu-id="82abe-160">-Command</span></span>

<span data-ttu-id="82abe-161">Выполняет указанные команды (с любыми параметрами) как введенные в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-161">Executes the specified commands (with any parameters) as though they were typed at the PowerShell command prompt.</span></span> <span data-ttu-id="82abe-162">После выполнения PowerShell завершает работу, если не указан параметр `-NoExit`.</span><span class="sxs-lookup"><span data-stu-id="82abe-162">After execution, PowerShell exits unless the `-NoExit` parameter is specified.</span></span>
<span data-ttu-id="82abe-163">Любой текст после `-Command` отправляется в PowerShell как одна командная строка.</span><span class="sxs-lookup"><span data-stu-id="82abe-163">Any text after `-Command` is sent as a single command line to PowerShell.</span></span> <span data-ttu-id="82abe-164">Это отличается от того, как `-File` обрабатывает параметры, передаваемые в скрипт.</span><span class="sxs-lookup"><span data-stu-id="82abe-164">This is different from how `-File` handles parameters sent to a script.</span></span>

<span data-ttu-id="82abe-165">Значением Command может быть строка "-".</span><span class="sxs-lookup"><span data-stu-id="82abe-165">The value of Command can be "-", a string.</span></span> <span data-ttu-id="82abe-166">или блок сценария.</span><span class="sxs-lookup"><span data-stu-id="82abe-166">or a script block.</span></span> <span data-ttu-id="82abe-167">Если для Command задано значение "-", текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="82abe-167">If the value of Command is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="82abe-168">Блоки скриптов должны быть заключены в скобки ({}).</span><span class="sxs-lookup"><span data-stu-id="82abe-168">Script blocks must be enclosed in braces ({}).</span></span> <span data-ttu-id="82abe-169">Указать блок сценария можно только при использовании PowerShell.exe в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82abe-169">You can specify a script block only when running PowerShell.exe in PowerShell.</span></span> <span data-ttu-id="82abe-170">Результаты сценария возвращаются родительской оболочке как десериализованные объекты XML, а не как активные объекты.</span><span class="sxs-lookup"><span data-stu-id="82abe-170">The results of the script are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="82abe-171">Если значением Command является строка, параметр **Command** должен быть последним в команде, так как любой знак, введенный после команды, интерпретируется как ее аргумент.</span><span class="sxs-lookup"><span data-stu-id="82abe-171">If the value of Command is a string, **Command** must be the last parameter in the command, because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="82abe-172">При написании строки для запуска команды PowerShell используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="82abe-172">To write a string that runs a PowerShell command, use the format:</span></span>

```powershell
"& {<command>}"
```

<span data-ttu-id="82abe-173">Кавычки обозначают строку, а оператор вызова (&) запускает выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="82abe-173">The quotation marks indicate a string and the invoke operator (&) causes the command to be executed.</span></span>

### <a name="-help---"></a><span data-ttu-id="82abe-174">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="82abe-174">-Help, -?, /?</span></span>

<span data-ttu-id="82abe-175">Показывает синтаксис powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="82abe-175">Shows the syntax of powershell.exe.</span></span> <span data-ttu-id="82abe-176">При вводе команды PowerShell.exe в PowerShell добавляйте в начало параметров команды дефис (-), а не косую черту (/).</span><span class="sxs-lookup"><span data-stu-id="82abe-176">If you are typing a PowerShell.exe command in PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="82abe-177">В Cmd.exe можно использовать как дефис, так и косую черту.</span><span class="sxs-lookup"><span data-stu-id="82abe-177">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="82abe-178">Замечание по устранению неполадок. Обратите внимание, что в PowerShell 2.0 запуск некоторых программ в консоли Windows PowerShell завершается ошибкой с кодом LastExitCode 0xc0000142.</span><span class="sxs-lookup"><span data-stu-id="82abe-178">Troubleshooting Note: In PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="82abe-179">ПРИМЕРЫ</span><span class="sxs-lookup"><span data-stu-id="82abe-179">EXAMPLES</span></span>

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
