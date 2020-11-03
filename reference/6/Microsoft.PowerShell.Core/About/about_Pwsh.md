---
description: Объясняет, как использовать `pwsh` интерфейс командной строки. Отображает параметры командной строки и описание синтаксиса.
keywords: powershell,командлет
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: 549c99fa618e2e53aed8945d95e92f97117aa6c9
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93232993"
---
# <a name="about-pwsh"></a><span data-ttu-id="4497e-105">О pwsh</span><span class="sxs-lookup"><span data-stu-id="4497e-105">About pwsh</span></span>

## <a name="short-description"></a><span data-ttu-id="4497e-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="4497e-106">Short Description</span></span>
<span data-ttu-id="4497e-107">Объясняет, как использовать `pwsh` интерфейс командной строки.</span><span class="sxs-lookup"><span data-stu-id="4497e-107">Explains how to use the `pwsh` command-line interface.</span></span> <span data-ttu-id="4497e-108">Отображает параметры командной строки и описание синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="4497e-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="4497e-109">Полное описание</span><span class="sxs-lookup"><span data-stu-id="4497e-109">Long Description</span></span>

## <a name="syntax"></a><span data-ttu-id="4497e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4497e-110">Syntax</span></span>

```
pwsh[.exe]
   [[-File] <filePath> [args]]
   [-Command { - | <script-block> [-args <arg-array>]
                 | <string> [<CommandParameters>] } ]
   [-ConfigurationName <string>]
   [-CustomPipeName <string>]
   [-EncodedCommand <Base64EncodedCommand>]
   [-ExecutionPolicy <ExecutionPolicy>]
   [-InputFormat {Text | XML}]
   [-Interactive]
   [-NoExit]
   [-NoLogo]
   [-NonInteractive]
   [-NoProfile]
   [-OutputFormat {Text | XML}]
   [-SettingsFile <SettingsFilePath>]
   [-Version]
   [-WindowStyle <style>]
   [-WorkingDirectory <directoryPath>]

pwsh[.exe] -h | -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="4497e-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="4497e-111">Parameters</span></span>

<span data-ttu-id="4497e-112">Все параметры не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="4497e-112">All parameters are case-insensitive.</span></span>

### <a name="-file---f"></a><span data-ttu-id="4497e-113">-File | -f</span><span class="sxs-lookup"><span data-stu-id="4497e-113">-File | -f</span></span>

<span data-ttu-id="4497e-114">Если значение `File` равно `-` , текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="4497e-114">If the value of `File` is `-`, the command text is read from standard input.</span></span>
<span data-ttu-id="4497e-115">Запуск `pwsh -File -` без перенаправленного стандартного ввода запускает обычный сеанс.</span><span class="sxs-lookup"><span data-stu-id="4497e-115">Running `pwsh -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="4497e-116">Это то же самое, что не указывает `File` параметр вообще.</span><span class="sxs-lookup"><span data-stu-id="4497e-116">This is the same as not specifying the `File` parameter at all.</span></span>

<span data-ttu-id="4497e-117">Это параметр по умолчанию, если параметры отсутствуют, но в командной строке есть значения.</span><span class="sxs-lookup"><span data-stu-id="4497e-117">This is the default parameter if no parameters are present but values are present in the command line.</span></span> <span data-ttu-id="4497e-118">Указанный скрипт выполняется в локальной области ("с источником с точкой"), поэтому функции и переменные, создаваемые сценарием, доступны в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4497e-118">The specified script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="4497e-119">Введите путь к файлу сценария и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="4497e-119">Enter the script file path and any parameters.</span></span> <span data-ttu-id="4497e-120">Файл должен быть последним параметром в команде, так как все символы, введенные после имени параметра файла, интерпретируется как путь к файлу скрипта, за которым следуют параметры сценария.</span><span class="sxs-lookup"><span data-stu-id="4497e-120">File must be the last parameter in the command, because all characters typed after the File parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="4497e-121">Обычно параметры-переключатели сценария включаются или опускаются.</span><span class="sxs-lookup"><span data-stu-id="4497e-121">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="4497e-122">Например, следующая команда использует параметр ALL файла скрипта Get-Script.ps1: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="4497e-122">For example, the following command uses the All parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="4497e-123">В редких случаях может потребоваться указать **логическое** значение для параметра Switch.</span><span class="sxs-lookup"><span data-stu-id="4497e-123">In rare cases, you might need to provide a **Boolean** value for a switch parameter.</span></span> <span data-ttu-id="4497e-124">Чтобы предоставить **логическое** значение для параметра-переключателя в значении параметра **File** , используйте параметр, обычно за которым следует двоеточие и логическое значение, как показано ниже: `-File .\Get-Script.ps1 -All:$False` .</span><span class="sxs-lookup"><span data-stu-id="4497e-124">To provide a **Boolean** value for a switch parameter in the value of the **File** parameter, Use the parameter normally followed immediately by a colon and the boolean value, such as the following: `-File .\Get-Script.ps1 -All:$False`.</span></span>

<span data-ttu-id="4497e-125">Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой).</span><span class="sxs-lookup"><span data-stu-id="4497e-125">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="4497e-126">Например, если вы используете `cmd.exe` и хотите передать значение переменной среды, используйте `cmd.exe` следующий синтаксис: `pwsh -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="4497e-126">For example, if you are in `cmd.exe` and want to pass an environment variable value, you would use the `cmd.exe` syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="4497e-127">В отличие от этого, выполнение `pwsh -File .\test.ps1 -TestParam $env:windir` в `cmd.exe` дает скрипт, получающий литеральную строку, `$env:windir` так как он не имеет специального значения для текущей `cmd.exe` оболочки.</span><span class="sxs-lookup"><span data-stu-id="4497e-127">In contrast, running `pwsh -File .\test.ps1 -TestParam $env:windir` in `cmd.exe` results in the script receiving the literal string `$env:windir` because it has no special meaning to the current `cmd.exe` shell.</span></span> <span data-ttu-id="4497e-128">`$env:windir`Стиль ссылки на переменную среды _можно_ использовать внутри параметра **команды** , так как он интерпретируется как код PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-128">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it is interpreted as PowerShell code.</span></span>

<span data-ttu-id="4497e-129">Аналогично, если вы хотите выполнить ту же команду из _пакетного скрипта_ , используйте `%~dp0` вместо `.\` или `$PSScriptRoot` для представления текущего каталога выполнения: `pwsh -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="4497e-129">Similarly, if you want to execute the same command from a _Batch script_ , you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `pwsh -File %~dp0test.ps1 -TestParam %windir%`.</span></span> <span data-ttu-id="4497e-130">Если вместо этого используется `.\test.ps1` , PowerShell выдаст ошибку, так как не может найти литеральный путь. `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="4497e-130">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="4497e-131">Когда файл скрипта завершается `exit` командой, код завершения процесса задается в виде числового аргумента, используемого с `exit` командой.</span><span class="sxs-lookup"><span data-stu-id="4497e-131">When the script file terminates with an `exit` command, the process exit code is set to the numeric argument used with the `exit` command.</span></span> <span data-ttu-id="4497e-132">При нормальном завершении код выхода всегда имеет значение `0` .</span><span class="sxs-lookup"><span data-stu-id="4497e-132">With normal termination, the exit code is always `0`.</span></span>

<span data-ttu-id="4497e-133">Как `-Command` и при возникновении ошибки, завершающей выполнение скрипта, код выхода имеет значение `1` .</span><span class="sxs-lookup"><span data-stu-id="4497e-133">Similar to `-Command`, when a script-terminating error occurs, the exit code is set to `1`.</span></span> <span data-ttu-id="4497e-134">Однако в отличие от `-Command` , когда выполнение прерывается с помощью <kbd>клавиши CTRL</kbd> - <kbd>C</kbd> , код выхода имеет значение `0` .</span><span class="sxs-lookup"><span data-stu-id="4497e-134">However, unlike with `-Command`, when the execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd> the exit code is `0`.</span></span>

### <a name="-command---c"></a><span data-ttu-id="4497e-135">-Command | -c</span><span class="sxs-lookup"><span data-stu-id="4497e-135">-Command | -c</span></span>

<span data-ttu-id="4497e-136">Выполняет указанные команды (и любые параметры), как если бы они были введены в командной строке PowerShell, а затем завершает работу, если `NoExit` не указан параметр.</span><span class="sxs-lookup"><span data-stu-id="4497e-136">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="4497e-137">Значение **команды** может быть `-` , блоком скрипта или строкой.</span><span class="sxs-lookup"><span data-stu-id="4497e-137">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="4497e-138">Если значение **Command** равно `-` , текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="4497e-138">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="4497e-139">Параметр **команды** принимает блок сценария только для выполнения, если он может распознать значение, передаваемое **команде** , в качестве типа **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="4497e-139">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="4497e-140">Это возможно _только_ при запуске `pwsh` с другого узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-140">This is _only_ possible when running `pwsh` from another PowerShell host.</span></span> <span data-ttu-id="4497e-141">Тип **ScriptBlock** может содержаться в существующей переменной, возвращенной из выражения, или в процессе анализа узлом PowerShell в виде литерального блока скрипта, заключенного в фигурные скобки ( `{}` ), перед передачей в `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="4497e-141">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `pwsh`.</span></span>

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="4497e-142">В не `cmd.exe` существует такого понятия, как блок сценария (или тип **ScriptBlock** ), поэтому значение, передаваемое **команде** , _всегда_ будет строкой.</span><span class="sxs-lookup"><span data-stu-id="4497e-142">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="4497e-143">Вы можете написать блок сценария в строке, но вместо выполнения его поведение будет таким, как если бы вы набирали его в типичном приглашении PowerShell, возвращая содержимое блока сценария обратно.</span><span class="sxs-lookup"><span data-stu-id="4497e-143">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="4497e-144">Строка, передаваемая **команде** , по-прежнему выполняется как код PowerShell, поэтому в первом месте при запуске из не требуется закрывающая фигурная скобка блока script `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="4497e-144">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="4497e-145">Для выполнения встроенного блока сценария, определенного внутри строки, можно использовать [оператор вызова](about_operators.md#special-operators) `&`.</span><span class="sxs-lookup"><span data-stu-id="4497e-145">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="4497e-146">Если значение **Command** является строкой, **команда** должна быть последним параметром для pwsh, так как все приведенные ниже аргументы будут интерпретироваться как часть выполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="4497e-146">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="4497e-147">При вызове из существующего сеанса PowerShell результаты возвращаются в родительскую оболочку как десериализованные объекты XML, а не в активные объекты.</span><span class="sxs-lookup"><span data-stu-id="4497e-147">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="4497e-148">Для других оболочек результаты возвращаются в виде строк.</span><span class="sxs-lookup"><span data-stu-id="4497e-148">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="4497e-149">Если значение **Command** равно `-` , текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="4497e-149">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="4497e-150">При использовании параметра **команды** со стандартным входом необходимо перенаправить стандартный ввод.</span><span class="sxs-lookup"><span data-stu-id="4497e-150">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="4497e-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="4497e-151">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="4497e-152">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="4497e-152">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="4497e-153">Код завершения процесса определяется состоянием последней команды (выполненной) в блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="4497e-153">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="4497e-154">Код выхода — `0` когда `$?` имеет значение `$true` или `1` когда `$?` имеет значение `$false` .</span><span class="sxs-lookup"><span data-stu-id="4497e-154">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="4497e-155">Если последняя команда является внешней программой или скриптом PowerShell, который явно задает код выхода, отличный от `0` или `1` , то код выхода преобразуется в `1` для кода завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="4497e-155">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="4497e-156">Чтобы сохранить конкретный код выхода, добавьте `exit $LASTEXITCODE` в командную строку или блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="4497e-156">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="4497e-157">Аналогичным образом, значение 1 возвращается при ошибке завершения скрипта (прекращение выполнения, завершающейся), например `throw` , или `-ErrorAction Stop` при прерывании выполнения с помощью <kbd>клавиши CTRL</kbd> - <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4497e-157">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

### <a name="-configurationname---config"></a><span data-ttu-id="4497e-158">-ConfigurationName | -config</span><span class="sxs-lookup"><span data-stu-id="4497e-158">-ConfigurationName | -config</span></span>

<span data-ttu-id="4497e-159">Указывает конечную точку конфигурации, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-159">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="4497e-160">Это может быть любая конечная точка, зарегистрированная на локальном компьютере, включая конечные точки удаленного взаимодействия PowerShell по умолчанию или пользовательскую конечную точку с конкретными возможностями роли пользователя.</span><span class="sxs-lookup"><span data-stu-id="4497e-160">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

<span data-ttu-id="4497e-161">Пример: `pwsh -ConfigurationName AdminRoles`</span><span class="sxs-lookup"><span data-stu-id="4497e-161">Example: `pwsh -ConfigurationName AdminRoles`</span></span>

### <a name="-custompipename"></a><span data-ttu-id="4497e-162">-Кустомпипенаме</span><span class="sxs-lookup"><span data-stu-id="4497e-162">-CustomPipeName</span></span>

<span data-ttu-id="4497e-163">Указывает имя, используемое для дополнительного сервера IPC (именованного канала), используемого для отладки и других межпроцессных соединений.</span><span class="sxs-lookup"><span data-stu-id="4497e-163">Specifies the name to use for an additional IPC server (named pipe) used for debugging and other cross-process communication.</span></span> <span data-ttu-id="4497e-164">Это обеспечивает предсказуемый механизм подключения к другим экземплярам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-164">This offers a predictable mechanism for connecting to other PowerShell instances.</span></span> <span data-ttu-id="4497e-165">Обычно используется с параметром **кустомпипенаме** в `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="4497e-165">Typically used with the **CustomPipeName** parameter on `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="4497e-166">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="4497e-166">This parameter was introduced in PowerShell 6.2.</span></span>

<span data-ttu-id="4497e-167">Пример:</span><span class="sxs-lookup"><span data-stu-id="4497e-167">For example:</span></span>

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a><span data-ttu-id="4497e-168">-Енкодедкомманд | -e | -EC</span><span class="sxs-lookup"><span data-stu-id="4497e-168">-EncodedCommand | -e | -ec</span></span>

<span data-ttu-id="4497e-169">Принимает строковую версию команды в кодировке Base64.</span><span class="sxs-lookup"><span data-stu-id="4497e-169">Accepts a Base64-encoded string version of a command.</span></span> <span data-ttu-id="4497e-170">Используйте этот параметр, чтобы отправлять команды в PowerShell, требующие сложных вложенных заключения в кавычки.</span><span class="sxs-lookup"><span data-stu-id="4497e-170">Use this parameter to submit commands to PowerShell that require complex, nested quoting.</span></span> <span data-ttu-id="4497e-171">Представление в формате Base64 должно быть строкой в кодировке UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4497e-171">The Base64 representation must be a UTF-16 encoded string.</span></span>

<span data-ttu-id="4497e-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="4497e-172">For example:</span></span>

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a><span data-ttu-id="4497e-173">-ExecutionPolicy | -ex | -EP</span><span class="sxs-lookup"><span data-stu-id="4497e-173">-ExecutionPolicy | -ex | -ep</span></span>

<span data-ttu-id="4497e-174">Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в `$env:PSExecutionPolicyPreference` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="4497e-174">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="4497e-175">Этот параметр не изменяет постоянно настроенные политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="4497e-175">This parameter does not change the persistently configured execution policies.</span></span>

<span data-ttu-id="4497e-176">Этот параметр применяется только к компьютерам Windows.</span><span class="sxs-lookup"><span data-stu-id="4497e-176">This parameter only applies to Windows computers.</span></span> <span data-ttu-id="4497e-177">`$env:PSExecutionPolicyPreference`Переменная среды не существует на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="4497e-177">The `$env:PSExecutionPolicyPreference` environment variable does not exist on non-Windows platforms.</span></span>

### <a name="-inputformat---in---if"></a><span data-ttu-id="4497e-178">-Инпутформат | -in | — Если</span><span class="sxs-lookup"><span data-stu-id="4497e-178">-InputFormat | -in | -if</span></span>

<span data-ttu-id="4497e-179">Описывает формат данных, отправляемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-179">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="4497e-180">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="4497e-180">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-interactive---i"></a><span data-ttu-id="4497e-181">-Interactive | -i</span><span class="sxs-lookup"><span data-stu-id="4497e-181">-Interactive | -i</span></span>

<span data-ttu-id="4497e-182">Предоставление пользователю интерактивного запроса.</span><span class="sxs-lookup"><span data-stu-id="4497e-182">Present an interactive prompt to the user.</span></span> <span data-ttu-id="4497e-183">Обратная для неинтерактивного параметра.</span><span class="sxs-lookup"><span data-stu-id="4497e-183">Inverse for NonInteractive parameter.</span></span>

### <a name="-noexit---noe"></a><span data-ttu-id="4497e-184">-Exit | -ное</span><span class="sxs-lookup"><span data-stu-id="4497e-184">-NoExit | -noe</span></span>

<span data-ttu-id="4497e-185">Не завершает работу после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="4497e-185">Does not exit after running startup commands.</span></span>

<span data-ttu-id="4497e-186">Пример: `pwsh -NoExit -Command Get-Date`</span><span class="sxs-lookup"><span data-stu-id="4497e-186">Example: `pwsh -NoExit -Command Get-Date`</span></span>

### <a name="-nologo---nol"></a><span data-ttu-id="4497e-187">-Неэмблема | -Нол</span><span class="sxs-lookup"><span data-stu-id="4497e-187">-NoLogo | -nol</span></span>

<span data-ttu-id="4497e-188">Скрывает баннер авторского права при запуске интерактивных сеансов.</span><span class="sxs-lookup"><span data-stu-id="4497e-188">Hides the copyright banner at startup of interactive sessions.</span></span>

### <a name="-noninteractive---noni"></a><span data-ttu-id="4497e-189">-Неинтерактивный | -Нони</span><span class="sxs-lookup"><span data-stu-id="4497e-189">-NonInteractive | -noni</span></span>

<span data-ttu-id="4497e-190">Не предоставляет пользователю интерактивную командную строку.</span><span class="sxs-lookup"><span data-stu-id="4497e-190">Does not present an interactive prompt to the user.</span></span> <span data-ttu-id="4497e-191">Любые попытки использования интерактивных функций, таких как `Read-Host` или запросы подтверждения, приводят к ошибкам, завершающим выполнение инструкции.</span><span class="sxs-lookup"><span data-stu-id="4497e-191">Any attempts to use interactive features, like `Read-Host` or confirmation prompts, result in statement-terminating errors.</span></span>

### <a name="-noprofile---nop"></a><span data-ttu-id="4497e-192">-Непрофиль | -NOP</span><span class="sxs-lookup"><span data-stu-id="4497e-192">-NoProfile | -nop</span></span>

<span data-ttu-id="4497e-193">Не загружает профили PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-193">Does not load the PowerShell profiles.</span></span>

### <a name="-outputformat---o---of"></a><span data-ttu-id="4497e-194">-OutputFormat | -o | -of</span><span class="sxs-lookup"><span data-stu-id="4497e-194">-OutputFormat | -o | -of</span></span>

<span data-ttu-id="4497e-195">Определяет формат выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-195">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="4497e-196">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="4497e-196">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

<span data-ttu-id="4497e-197">Пример: `pwsh -o XML -c Get-Date`</span><span class="sxs-lookup"><span data-stu-id="4497e-197">Example: `pwsh -o XML -c Get-Date`</span></span>

<span data-ttu-id="4497e-198">При вызове с помощью сеанса PowerShell вы получаете десериализованные объекты как выходные данные, а не обычные строки.</span><span class="sxs-lookup"><span data-stu-id="4497e-198">When called withing a PowerShell session, you get deserialized objects as output rather plain strings.</span></span> <span data-ttu-id="4497e-199">При вызове из других оболочек выходными данными являются строковые данные, отформатированные как текст CLIXML.</span><span class="sxs-lookup"><span data-stu-id="4497e-199">When called from other shells, the output is string data formatted as CLIXML text.</span></span>

### <a name="-settingsfile---settings"></a><span data-ttu-id="4497e-200">-SettingsFile | -параметры</span><span class="sxs-lookup"><span data-stu-id="4497e-200">-SettingsFile | -settings</span></span>

<span data-ttu-id="4497e-201">Переопределяет файл параметров на уровне системы `powershell.config.json` для сеанса.</span><span class="sxs-lookup"><span data-stu-id="4497e-201">Overrides the system-wide `powershell.config.json` settings file for the session.</span></span> <span data-ttu-id="4497e-202">По умолчанию параметры на уровне системы считываются из в `powershell.config.json` `$PSHOME` каталоге.</span><span class="sxs-lookup"><span data-stu-id="4497e-202">By default, system-wide settings are read from the `powershell.config.json` in the `$PSHOME` directory.</span></span>

<span data-ttu-id="4497e-203">Обратите внимание, что эти параметры не используются конечной точкой, заданной `-ConfigurationName` аргументом.</span><span class="sxs-lookup"><span data-stu-id="4497e-203">Note that these settings are not used by the endpoint specified by the `-ConfigurationName` argument.</span></span>

<span data-ttu-id="4497e-204">Пример: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span><span class="sxs-lookup"><span data-stu-id="4497e-204">Example: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span></span>

### <a name="-sshservermode---sshs"></a><span data-ttu-id="4497e-205">-Сшсервермоде | -сшс</span><span class="sxs-lookup"><span data-stu-id="4497e-205">-SSHServerMode | -sshs</span></span>

<span data-ttu-id="4497e-206">Используется в sshd_config для запуска PowerShell в качестве подсистемы SSH.</span><span class="sxs-lookup"><span data-stu-id="4497e-206">Used in sshd_config for running PowerShell as an SSH subsystem.</span></span> <span data-ttu-id="4497e-207">Он не предназначен для использования в каких-либо других целях.</span><span class="sxs-lookup"><span data-stu-id="4497e-207">It is not intended or supported for any other use.</span></span>

### <a name="-version---v"></a><span data-ttu-id="4497e-208">-Version | -v</span><span class="sxs-lookup"><span data-stu-id="4497e-208">-Version | -v</span></span>

<span data-ttu-id="4497e-209">Отображает версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-209">Displays the version of PowerShell.</span></span> <span data-ttu-id="4497e-210">Дополнительные параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="4497e-210">Additional parameters are ignored.</span></span>

### <a name="-windowstyle---w"></a><span data-ttu-id="4497e-211">-WindowStyle | -w</span><span class="sxs-lookup"><span data-stu-id="4497e-211">-WindowStyle | -w</span></span>

<span data-ttu-id="4497e-212">Задает стиль окна для сеанса.</span><span class="sxs-lookup"><span data-stu-id="4497e-212">Sets the window style for the session.</span></span> <span data-ttu-id="4497e-213">Допустимые значения: Normal, Minimized, Maximized и Hidden.</span><span class="sxs-lookup"><span data-stu-id="4497e-213">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-workingdirectory---wd"></a><span data-ttu-id="4497e-214">-WorkingDirectory | — WD</span><span class="sxs-lookup"><span data-stu-id="4497e-214">-WorkingDirectory | -wd</span></span>

<span data-ttu-id="4497e-215">Задает начальный рабочий каталог, выполняя при запуске.</span><span class="sxs-lookup"><span data-stu-id="4497e-215">Sets the initial working directory by executing at startup.</span></span> <span data-ttu-id="4497e-216">Поддерживается любой допустимый путь к файлу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4497e-216">Any valid PowerShell file path is supported.</span></span>

<span data-ttu-id="4497e-217">Чтобы запустить PowerShell в домашнем каталоге, используйте: `pwsh -WorkingDirectory ~`</span><span class="sxs-lookup"><span data-stu-id="4497e-217">To start PowerShell in your home directory, use: `pwsh -WorkingDirectory ~`</span></span>

### <a name="-help---"></a><span data-ttu-id="4497e-218">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="4497e-218">-Help, -?, /?</span></span>

<span data-ttu-id="4497e-219">Отображает справку для `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="4497e-219">Displays help for `pwsh`.</span></span> <span data-ttu-id="4497e-220">При вводе команды pwsh в PowerShell добавляйте параметры команды с дефисом ( `-` ), а не косой чертой ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="4497e-220">If you are typing a pwsh command in PowerShell, prepend the command parameters with a hyphen (`-`), not a forward slash (`/`).</span></span>
