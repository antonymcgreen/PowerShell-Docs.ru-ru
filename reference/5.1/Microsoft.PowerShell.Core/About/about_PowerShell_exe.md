---
description: Объясняет, как использовать `powershell.exe` интерфейс командной строки. Отображает параметры командной строки и описание синтаксиса.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: ef03558a6b58868b98c9da488934b0bfbbce9fe7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232330"
---
# <a name="about-powershellexe"></a><span data-ttu-id="337b6-105">О PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="337b6-105">About PowerShell.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="337b6-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="337b6-106">Short Description</span></span>
<span data-ttu-id="337b6-107">Объясняет, как использовать `powershell.exe` интерфейс командной строки.</span><span class="sxs-lookup"><span data-stu-id="337b6-107">Explains how to use the `powershell.exe` command-line interface.</span></span> <span data-ttu-id="337b6-108">Отображает параметры командной строки и описание синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="337b6-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="337b6-109">Полное описание</span><span class="sxs-lookup"><span data-stu-id="337b6-109">Long Description</span></span>

### <a name="syntax"></a><span data-ttu-id="337b6-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="337b6-110">SYNTAX</span></span>

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a><span data-ttu-id="337b6-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="337b6-111">Parameters</span></span>

#### <a name="-psconsolefile-filepath"></a><span data-ttu-id="337b6-112">-PSConsoleFile \<FilePath\></span><span class="sxs-lookup"><span data-stu-id="337b6-112">-PSConsoleFile \<FilePath\></span></span>

<span data-ttu-id="337b6-113">Загружает указанный файл консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-113">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="337b6-114">Введите путь и имя файла консоли.</span><span class="sxs-lookup"><span data-stu-id="337b6-114">Enter the path and name of the console file.</span></span> <span data-ttu-id="337b6-115">Для создания файла консоли используйте командлет Export-Console в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-115">To create a console file, use the Export-Console cmdlet in PowerShell.</span></span>

#### <a name="-version-powershell-version"></a><span data-ttu-id="337b6-116">-Version \<PowerShell Version\></span><span class="sxs-lookup"><span data-stu-id="337b6-116">-Version \<PowerShell Version\></span></span>

<span data-ttu-id="337b6-117">Запускает заданную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-117">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="337b6-118">Допустимые значения: 2.0 и 3.0.</span><span class="sxs-lookup"><span data-stu-id="337b6-118">Valid values are 2.0 and 3.0.</span></span> <span data-ttu-id="337b6-119">Указанная версия должна быть установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="337b6-119">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="337b6-120">Если на компьютере установлена оболочка Windows PowerShell 3,0, версия по умолчанию — 3,0.</span><span class="sxs-lookup"><span data-stu-id="337b6-120">If Windows PowerShell 3.0 is installed on the computer, "3.0" is the default version.</span></span>
<span data-ttu-id="337b6-121">В противном случае версия по умолчанию — "2,0".</span><span class="sxs-lookup"><span data-stu-id="337b6-121">Otherwise, "2.0" is the default version.</span></span> <span data-ttu-id="337b6-122">Дополнительные сведения см. в разделе [Установка PowerShell](/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="337b6-122">For more information, see [Installing PowerShell](/powershell/scripting/install/installing-windows-powershell).</span></span>

#### <a name="-nologo"></a><span data-ttu-id="337b6-123">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="337b6-123">-NoLogo</span></span>

<span data-ttu-id="337b6-124">Скрывает баннер авторских прав при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="337b6-124">Hides the copyright banner at startup.</span></span>

#### <a name="-noexit"></a><span data-ttu-id="337b6-125">-NoExit</span><span class="sxs-lookup"><span data-stu-id="337b6-125">-NoExit</span></span>

<span data-ttu-id="337b6-126">Не завершает работу после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="337b6-126">Does not exit after running startup commands.</span></span>

#### <a name="-sta"></a><span data-ttu-id="337b6-127">-Sta</span><span class="sxs-lookup"><span data-stu-id="337b6-127">-Sta</span></span>

<span data-ttu-id="337b6-128">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="337b6-128">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="337b6-129">В Windows PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="337b6-129">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="337b6-130">В Windows PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="337b6-130">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-mta"></a><span data-ttu-id="337b6-131">-Mta</span><span class="sxs-lookup"><span data-stu-id="337b6-131">-Mta</span></span>

<span data-ttu-id="337b6-132">Запускает PowerShell с использованием многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="337b6-132">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="337b6-133">Этот параметр впервые появился в PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="337b6-133">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="337b6-134">В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).</span><span class="sxs-lookup"><span data-stu-id="337b6-134">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="337b6-135">В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="337b6-135">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-noprofile"></a><span data-ttu-id="337b6-136">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="337b6-136">-NoProfile</span></span>

<span data-ttu-id="337b6-137">Не загружает профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-137">Does not load the PowerShell profile.</span></span>

#### <a name="-noninteractive"></a><span data-ttu-id="337b6-138">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="337b6-138">-NonInteractive</span></span>

<span data-ttu-id="337b6-139">Не предоставляет пользователю интерактивную командную строку.</span><span class="sxs-lookup"><span data-stu-id="337b6-139">Does not present an interactive prompt to the user.</span></span>

#### <a name="-inputformat-text--xml"></a><span data-ttu-id="337b6-140">-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="337b6-140">-InputFormat {Text | XML}</span></span>

<span data-ttu-id="337b6-141">Описывает формат данных, отправляемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-141">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="337b6-142">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="337b6-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-outputformat-text--xml"></a><span data-ttu-id="337b6-143">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="337b6-143">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="337b6-144">Определяет формат выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-144">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="337b6-145">Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).</span><span class="sxs-lookup"><span data-stu-id="337b6-145">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-windowstyle-window-style"></a><span data-ttu-id="337b6-146">-WindowStyle \<Window style\></span><span class="sxs-lookup"><span data-stu-id="337b6-146">-WindowStyle \<Window style\></span></span>

<span data-ttu-id="337b6-147">Задает стиль окна для сеанса.</span><span class="sxs-lookup"><span data-stu-id="337b6-147">Sets the window style for the session.</span></span> <span data-ttu-id="337b6-148">Допустимые значения: Normal, Minimized, Maximized и Hidden.</span><span class="sxs-lookup"><span data-stu-id="337b6-148">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

#### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="337b6-149">-EncodedCommand \<Base64EncodedCommand\></span><span class="sxs-lookup"><span data-stu-id="337b6-149">-EncodedCommand \<Base64EncodedCommand\></span></span>

<span data-ttu-id="337b6-150">Принимает строковую версию команды в кодировке Base 64.</span><span class="sxs-lookup"><span data-stu-id="337b6-150">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="337b6-151">Используйте этот параметр для отправки в PowerShell команд, требующих сложных кавычек или фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="337b6-151">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span> <span data-ttu-id="337b6-152">Строка должна быть отформатирована с использованием кодировки UTF-16LE.</span><span class="sxs-lookup"><span data-stu-id="337b6-152">The string must be formatted using UTF-16LE character encoding.</span></span>

#### <a name="-configurationname-string"></a><span data-ttu-id="337b6-153">-ConfigurationName \<string\></span><span class="sxs-lookup"><span data-stu-id="337b6-153">-ConfigurationName \<string\></span></span>

<span data-ttu-id="337b6-154">Указывает конечную точку конфигурации, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-154">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="337b6-155">Это может быть любая конечная точка, зарегистрированная на локальном компьютере, включая конечные точки удаленного взаимодействия PowerShell по умолчанию или пользовательскую конечную точку с конкретными возможностями роли пользователя.</span><span class="sxs-lookup"><span data-stu-id="337b6-155">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

#### <a name="-file----filepath-args"></a><span data-ttu-id="337b6-156">-File-| \<filePath\>\<args\></span><span class="sxs-lookup"><span data-stu-id="337b6-156">-File - | \<filePath\> \<args\></span></span>

<span data-ttu-id="337b6-157">Если значение **File** равно "-", текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="337b6-157">If the value of **File** is "-", the command text is read from standard input.</span></span>
<span data-ttu-id="337b6-158">Запуск `powershell -File -` без перенаправленного стандартного ввода запускает обычный сеанс.</span><span class="sxs-lookup"><span data-stu-id="337b6-158">Running `powershell -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="337b6-159">Это то же самое, что не указывает параметр **файла** .</span><span class="sxs-lookup"><span data-stu-id="337b6-159">This is the same as not specifying the **File** parameter at all.</span></span>

<span data-ttu-id="337b6-160">Если значение **файла** является путем к файлу, сценарий выполняется в локальной области ("с последовательной точкой"), чтобы функции и переменные, создаваемые сценарием, были доступны в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="337b6-160">If the value of **File** is a file path, the script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="337b6-161">Введите путь к файлу сценария и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="337b6-161">Enter the script file path and any parameters.</span></span> <span data-ttu-id="337b6-162">**File** должен быть последним параметром в команде.</span><span class="sxs-lookup"><span data-stu-id="337b6-162">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="337b6-163">Все значения, введенные после параметра **File** , обрабатываются как путь к файлу скрипта и параметры, передаваемые этому скрипту.</span><span class="sxs-lookup"><span data-stu-id="337b6-163">All values typed after the **File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="337b6-164">Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой).</span><span class="sxs-lookup"><span data-stu-id="337b6-164">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="337b6-165">Например, если вы используете **cmd.exe** и хотите передать значение переменной среды, используйте синтаксис **cmd.exe** : `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="337b6-165">For example, if you are in **cmd.exe** and want to pass an environment variable value, you would use the **cmd.exe** syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="337b6-166">В отличие от этого, выполнение `powershell.exe -File .\test.ps1 -TestParam $env:windir` в **cmd.exe** приводит к получению сценария, получающего литеральную строку, `$env:windir` так как она не имеет специального значения для текущей оболочки **cmd.exe** .</span><span class="sxs-lookup"><span data-stu-id="337b6-166">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in **cmd.exe** results in the script receiving the literal string `$env:windir` because it has no special meaning to the current **cmd.exe** shell.</span></span> <span data-ttu-id="337b6-167">`$env:windir`Стиль ссылки на переменную среды _можно_ использовать внутри параметра **команды** , так как он будет интерпретирован как код PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-167">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it will be interpreted as PowerShell code.</span></span>

<span data-ttu-id="337b6-168">Аналогично, если вы хотите выполнить ту же команду из **пакетного скрипта** , используйте `%~dp0` вместо `.\` или `$PSScriptRoot` для представления текущего каталога выполнения: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="337b6-168">Similarly, if you want to execute the same command from a **Batch script** , you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%`.</span></span>
<span data-ttu-id="337b6-169">Если вместо этого используется `.\test.ps1` , PowerShell выдаст ошибку, так как не может найти литеральный путь. `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="337b6-169">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="337b6-170">Если значение **File** является путем к файлу, то **File** _должен_ быть последним параметром в команде, так как все символы, введенные после имени параметра **файла** , будут интерпретированы как путь к файлу скрипта, за которым следуют параметры сценария.</span><span class="sxs-lookup"><span data-stu-id="337b6-170">When the value of **File** is a file path, **File** _must_ be the last parameter in the command because any characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="337b6-171">Можно включить параметры и значения скрипта в значение параметра **File** .</span><span class="sxs-lookup"><span data-stu-id="337b6-171">You can include the script parameters and values in the value of the **File** parameter.</span></span> <span data-ttu-id="337b6-172">Пример: `-File .\Get-Script.ps1 -Domain Central`</span><span class="sxs-lookup"><span data-stu-id="337b6-172">For example: `-File .\Get-Script.ps1 -Domain Central`</span></span>

<span data-ttu-id="337b6-173">Обычно параметры-переключатели сценария включаются или опускаются.</span><span class="sxs-lookup"><span data-stu-id="337b6-173">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="337b6-174">Например, следующая команда использует параметр **ALL** `Get-Script.ps1` файла скрипта: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="337b6-174">For example, the following command uses the **All** parameter of the `Get-Script.ps1` script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="337b6-175">В редких случаях может потребоваться указать **логическое** значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="337b6-175">In rare cases, you might need to provide a **Boolean** value for a parameter.</span></span>
<span data-ttu-id="337b6-176">Невозможно передать явное логическое значение для параметра Switch при выполнении сценария таким образом.</span><span class="sxs-lookup"><span data-stu-id="337b6-176">It is not possible to pass an explicit boolean value for a switch parameter when running a script in this way.</span></span> <span data-ttu-id="337b6-177">Это ограничение было удалено в PowerShell 6 ( `pwsh.exe` ).</span><span class="sxs-lookup"><span data-stu-id="337b6-177">This limitation was removed in PowerShell 6 (`pwsh.exe`).</span></span>

#### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="337b6-178">-ExecutionPolicy \<ExecutionPolicy\></span><span class="sxs-lookup"><span data-stu-id="337b6-178">-ExecutionPolicy \<ExecutionPolicy\></span></span>

<span data-ttu-id="337b6-179">Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в `$env:PSExecutionPolicyPreference` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="337b6-179">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="337b6-180">Этот параметр не изменяет политику выполнения PowerShell, заданную в реестре.</span><span class="sxs-lookup"><span data-stu-id="337b6-180">This parameter does not change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="337b6-181">Дополнительные сведения о политиках выполнения PowerShell, включая список допустимых значений, см. в статье [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="337b6-181">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

#### <a name="-command"></a><span data-ttu-id="337b6-182">-Command</span><span class="sxs-lookup"><span data-stu-id="337b6-182">-Command</span></span>

<span data-ttu-id="337b6-183">Выполняет указанные команды (и любые параметры), как если бы они были введены в командной строке PowerShell, а затем завершает работу, если `NoExit` не указан параметр.</span><span class="sxs-lookup"><span data-stu-id="337b6-183">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="337b6-184">Значение **команды** может быть `-` , блоком скрипта или строкой.</span><span class="sxs-lookup"><span data-stu-id="337b6-184">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="337b6-185">Если значение **Command** равно `-` , текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="337b6-185">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="337b6-186">Параметр **команды** принимает блок сценария только для выполнения, если он может распознать значение, передаваемое **команде** , в качестве типа **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="337b6-186">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="337b6-187">Это возможно _только_ при запуске `powershell.exe` с другого узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-187">This is _only_ possible when running `powershell.exe` from another PowerShell host.</span></span> <span data-ttu-id="337b6-188">Тип **ScriptBlock** может содержаться в существующей переменной, возвращенной из выражения, или в процессе анализа узлом PowerShell в виде литерального блока скрипта, заключенного в фигурные скобки ( `{}` ), перед передачей в `powershell.exe` .</span><span class="sxs-lookup"><span data-stu-id="337b6-188">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `powershell.exe`.</span></span>

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="337b6-189">В не `cmd.exe` существует такого понятия, как блок сценария (или тип **ScriptBlock** ), поэтому значение, передаваемое **команде** , _всегда_ будет строкой.</span><span class="sxs-lookup"><span data-stu-id="337b6-189">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="337b6-190">Вы можете написать блок сценария в строке, но вместо выполнения его поведение будет таким, как если бы вы набирали его в типичном приглашении PowerShell, возвращая содержимое блока сценария обратно.</span><span class="sxs-lookup"><span data-stu-id="337b6-190">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="337b6-191">Строка, передаваемая **команде** , по-прежнему выполняется как код PowerShell, поэтому в первом месте при запуске из не требуется закрывающая фигурная скобка блока script `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="337b6-191">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="337b6-192">Для выполнения встроенного блока сценария, определенного внутри строки, можно использовать [оператор вызова](about_operators.md#special-operators) `&`.</span><span class="sxs-lookup"><span data-stu-id="337b6-192">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```cmd
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="337b6-193">Если значение **Command** является строкой, **команда** должна быть последним параметром для pwsh, так как все приведенные ниже аргументы будут интерпретироваться как часть выполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="337b6-193">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="337b6-194">При вызове из существующего сеанса PowerShell результаты возвращаются в родительскую оболочку как десериализованные объекты XML, а не в активные объекты.</span><span class="sxs-lookup"><span data-stu-id="337b6-194">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="337b6-195">Для других оболочек результаты возвращаются в виде строк.</span><span class="sxs-lookup"><span data-stu-id="337b6-195">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="337b6-196">Если значение **Command** равно `-` , текст команды считывается из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="337b6-196">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="337b6-197">При использовании параметра **команды** со стандартным входом необходимо перенаправить стандартный ввод.</span><span class="sxs-lookup"><span data-stu-id="337b6-197">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="337b6-198">Пример:</span><span class="sxs-lookup"><span data-stu-id="337b6-198">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="337b6-199">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="337b6-199">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="337b6-200">Код завершения процесса определяется состоянием последней команды (выполненной) в блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="337b6-200">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="337b6-201">Код выхода — `0` когда `$?` имеет значение `$true` или `1` когда `$?` имеет значение `$false` .</span><span class="sxs-lookup"><span data-stu-id="337b6-201">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="337b6-202">Если последняя команда является внешней программой или скриптом PowerShell, который явно задает код выхода, отличный от `0` или `1` , то код выхода преобразуется в `1` для кода завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="337b6-202">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="337b6-203">Чтобы сохранить конкретный код выхода, добавьте `exit $LASTEXITCODE` в командную строку или блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="337b6-203">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="337b6-204">Аналогичным образом, значение 1 возвращается при ошибке завершения скрипта (прекращение выполнения, завершающейся), например `throw` , или `-ErrorAction Stop` при прерывании выполнения с помощью <kbd>клавиши CTRL</kbd> - <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="337b6-204">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

<span data-ttu-id="337b6-205">возможно _только_ при запуске **PowerShell.exe** с другого узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="337b6-205">_only_ possible when running **PowerShell.exe** from another PowerShell host.</span></span>
<span data-ttu-id="337b6-206">Тип **ScriptBlock** может содержаться в существующей переменной, возвращенной из выражения, или в виде литерального блока сценария, заключенного в фигурные скобки `{}` , перед передачей в **PowerShell.exe**.</span><span class="sxs-lookup"><span data-stu-id="337b6-206">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to **PowerShell.exe**.</span></span>

<span data-ttu-id="337b6-207">В **cmd.exe** не существует такого понятия, как блок сценария (или тип **ScriptBlock** ), поэтому значение, передаваемое **команде** , _всегда_ будет строкой.</span><span class="sxs-lookup"><span data-stu-id="337b6-207">In **cmd.exe** , there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="337b6-208">Вы можете написать блок сценария в строке, но вместо выполнения его поведение будет таким, как если бы вы набирали его в типичном приглашении PowerShell, возвращая содержимое блока сценария обратно.</span><span class="sxs-lookup"><span data-stu-id="337b6-208">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="337b6-209">Строка, передаваемая **команде** , по-прежнему будет выполняться как PowerShell, поэтому в первом месте при запуске из **cmd.exe** часто не требуются фигурные скобки блока script.</span><span class="sxs-lookup"><span data-stu-id="337b6-209">A string passed to **Command** will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from **cmd.exe**.</span></span> <span data-ttu-id="337b6-210">Чтобы выполнить встроенный блок скрипта, определенный внутри строки, можно использовать [оператор Call](about_operators.md#special-operators) 
 `&` :</span><span class="sxs-lookup"><span data-stu-id="337b6-210">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators)
`&` can be used:</span></span>

```console
"& {<command>}"
```

#### <a name="-help---"></a><span data-ttu-id="337b6-211">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="337b6-211">-Help, -?, /?</span></span>

<span data-ttu-id="337b6-212">Отображает справку для **PowerShell.exe**.</span><span class="sxs-lookup"><span data-stu-id="337b6-212">Displays help for **PowerShell.exe**.</span></span> <span data-ttu-id="337b6-213">При вводе команды **PowerShell.exe** в сеансе PowerShell перед параметрами команды используется дефис (-), а не косая черта (/).</span><span class="sxs-lookup"><span data-stu-id="337b6-213">If you are typing a **PowerShell.exe** command in a PowerShell session, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="337b6-214">В **cmd.exe** можно использовать дефис или прямую косую черту.</span><span class="sxs-lookup"><span data-stu-id="337b6-214">You can use either a hyphen or forward slash in **cmd.exe**.</span></span>

### <a name="remarks"></a><span data-ttu-id="337b6-215">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="337b6-215">REMARKS</span></span>

<span data-ttu-id="337b6-216">Устранение неполадок Примечание. в PowerShell 2,0 запуск некоторых программ из консоли PowerShell завершается сбоем с **LastExitCode** 0xc0000142.</span><span class="sxs-lookup"><span data-stu-id="337b6-216">Troubleshooting note: In PowerShell 2.0, starting some programs from the PowerShell console fails with a **LastExitCode** of 0xc0000142.</span></span>

### <a name="examples"></a><span data-ttu-id="337b6-217">Примеры</span><span class="sxs-lookup"><span data-stu-id="337b6-217">EXAMPLES</span></span>

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
