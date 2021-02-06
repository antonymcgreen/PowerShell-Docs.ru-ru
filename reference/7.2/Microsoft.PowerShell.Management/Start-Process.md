---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: 28f343ddc6021e129d3eae007114b93ed17d5e95
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604488"
---
# <span data-ttu-id="567d0-102">Start-Process</span><span class="sxs-lookup"><span data-stu-id="567d0-102">Start-Process</span></span>

## <span data-ttu-id="567d0-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="567d0-103">SYNOPSIS</span></span>
<span data-ttu-id="567d0-104">Запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="567d0-104">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="567d0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="567d0-105">SYNTAX</span></span>

### <span data-ttu-id="567d0-106">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="567d0-106">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="567d0-107">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="567d0-107">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="567d0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="567d0-108">DESCRIPTION</span></span>

<span data-ttu-id="567d0-109">`Start-Process`Командлет запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="567d0-109">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="567d0-110">По умолчанию `Start-Process` создает новый процесс, который наследует все переменные среды, определенные в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="567d0-110">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="567d0-111">Чтобы указать программу, выполняемую в процессе, введите исполняемый файл или файл скрипта, либо файл, который может быть открыт с помощью имеющейся на компьютере программы.</span><span class="sxs-lookup"><span data-stu-id="567d0-111">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="567d0-112">Если указан неисполняемый файл, `Start-Process` программа запускает программу, связанную с файлом, аналогично `Invoke-Item` командлету.</span><span class="sxs-lookup"><span data-stu-id="567d0-112">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="567d0-113">Параметры можно использовать `Start-Process` для указания параметров, таких как загрузка профиля пользователя, запуск процесса в новом окне или использование альтернативных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="567d0-113">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="567d0-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="567d0-114">EXAMPLES</span></span>

### <span data-ttu-id="567d0-115">Пример 1. Запуск процесса, использующего значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="567d0-115">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="567d0-116">В этом примере запускается процесс, который использует `Sort.exe` файл в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="567d0-116">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="567d0-117">Команда использует все значения по умолчанию, включая стиль окна по умолчанию, рабочую папку и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="567d0-117">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="567d0-118">Пример 2. Печать текстового файла</span><span class="sxs-lookup"><span data-stu-id="567d0-118">Example 2: Print a text file</span></span>

<span data-ttu-id="567d0-119">В этом примере запускается процесс, который выводит `C:\PS-Test\MyFile.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-119">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="567d0-120">Пример 3. Запуск процесса для сортировки элементов в новый файл</span><span class="sxs-lookup"><span data-stu-id="567d0-120">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="567d0-121">В этом примере запускается процесс, который сортирует элементы в `Testsort.txt` файле и возвращает отсортированные элементы в `Sorted.txt` файлах.</span><span class="sxs-lookup"><span data-stu-id="567d0-121">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="567d0-122">Все ошибки записываются в `SortError.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-122">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="567d0-123">Параметр **усеневенвиронмент** указывает, что процесс выполняется с собственными переменными среды.</span><span class="sxs-lookup"><span data-stu-id="567d0-123">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="567d0-124">Пример 4. Запуск процесса в развернутом окне</span><span class="sxs-lookup"><span data-stu-id="567d0-124">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="567d0-125">В этом примере запускается `Notepad.exe` процесс.</span><span class="sxs-lookup"><span data-stu-id="567d0-125">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="567d0-126">Окно разворачивается во весь экран и удерживается до завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="567d0-126">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="567d0-127">Пример 5. Запуск PowerShell от имени администратора</span><span class="sxs-lookup"><span data-stu-id="567d0-127">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="567d0-128">В этом примере запускается PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="567d0-128">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="567d0-129">Пример 6. Использование различных команд для запуска процесса</span><span class="sxs-lookup"><span data-stu-id="567d0-129">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="567d0-130">В этом примере показано, как найти команды, которые можно использовать при запуске процесса.</span><span class="sxs-lookup"><span data-stu-id="567d0-130">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="567d0-131">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="567d0-131">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="567d0-132">В примере используется `New-Object` для создания объекта **System. Diagnostics. ProcessStartInfo** для **PowerShell.exe**— файла, который выполняется в процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d0-132">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe**, the file that runs in the PowerShell process.</span></span> <span data-ttu-id="567d0-133">Свойство **Verbs** объекта **ProcessStartInfo** показывает, что можно использовать команды **Open** и **runas** с `PowerShell.exe` или с любым процессом, запускающим `.exe` файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-133">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="567d0-134">Пример 7. Указание аргументов для процесса</span><span class="sxs-lookup"><span data-stu-id="567d0-134">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="567d0-135">Обе команды запускают интерпретатор команд Windows, выполняя `dir` команду в `Program Files` папке.</span><span class="sxs-lookup"><span data-stu-id="567d0-135">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="567d0-136">Поскольку это переключка содержит пробел, значение должно заключаться в экранированные кавычки.</span><span class="sxs-lookup"><span data-stu-id="567d0-136">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="567d0-137">Обратите внимание, что первая команда указывает строку как **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="567d0-137">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="567d0-138">Вторая команда является массивом строк.</span><span class="sxs-lookup"><span data-stu-id="567d0-138">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

### <span data-ttu-id="567d0-139">Пример 8. Создание отсоединенного процесса в Linux</span><span class="sxs-lookup"><span data-stu-id="567d0-139">Example 8: Create a detached process on Linux</span></span>

<span data-ttu-id="567d0-140">В Windows `Start-Process` создает независимый процесс, который остается запущенным независимо от запуска оболочки.</span><span class="sxs-lookup"><span data-stu-id="567d0-140">On Windows, `Start-Process` creates an independent process that remains running independently of the launching shell.</span></span> <span data-ttu-id="567d0-141">На платформах, отличных от Windows, вновь запущенный процесс прикрепляется к запущенной оболочке.</span><span class="sxs-lookup"><span data-stu-id="567d0-141">On non-Windows platforms, the newly started process is attached to the shell that launched.</span></span> <span data-ttu-id="567d0-142">Если закрывается Запуск оболочки, дочерний процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="567d0-142">If the launching shell is closed, the child process is terminated.</span></span>

<span data-ttu-id="567d0-143">Во избежание завершения дочернего процесса на платформах, подобных Unix, можно сочетать `Start-Process` с `nohup` .</span><span class="sxs-lookup"><span data-stu-id="567d0-143">To avoid terminating the child process on Unix-like platforms, you can combine `Start-Process` with `nohup`.</span></span> <span data-ttu-id="567d0-144">В следующем примере запускается фоновый экземпляр PowerShell в Linux, который остается активным даже после закрытия сеанса запуска.</span><span class="sxs-lookup"><span data-stu-id="567d0-144">The following example launches a background instance of PowerShell on Linux that stays alive even after you close the launching session.</span></span> <span data-ttu-id="567d0-145">`nohup`Команда собирает выходные данные в файле `nohup.out` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="567d0-145">The `nohup` command collects output in file `nohup.out` in the current directory.</span></span>

```powershell
# Runs for 2 minutes and appends output to ./nohup.out
Start-Process nohup 'pwsh -noprofile -c "1..120 | % { Write-Host . -NoNewline; sleep 1 }"'
```

<span data-ttu-id="567d0-146">В этом примере `Start-Process` выполняет `nohup` команду Linux, которая запускается `pwsh` как отсоединенный процесс.</span><span class="sxs-lookup"><span data-stu-id="567d0-146">In this example, `Start-Process` is running the Linux `nohup` command, which launches `pwsh` as a detached process.</span></span> <span data-ttu-id="567d0-147">Дополнительные сведения см. на справочной странице [нохуп](https://linux.die.net/man/1/nohup).</span><span class="sxs-lookup"><span data-stu-id="567d0-147">For more information, see the man page for [nohup](https://linux.die.net/man/1/nohup).</span></span>

## <span data-ttu-id="567d0-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="567d0-148">PARAMETERS</span></span>

### <span data-ttu-id="567d0-149">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="567d0-149">-ArgumentList</span></span>

<span data-ttu-id="567d0-150">Указывает параметры или значения параметров, которые следует использовать при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="567d0-150">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="567d0-151">Аргументы можно принимать как одну строку с аргументами, разделенными пробелами, или как массив строк, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="567d0-151">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="567d0-152">Если параметры или значения параметров содержат пробел, их необходимо заключить в escape-символы, заключенные в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="567d0-152">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="567d0-153">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="567d0-153">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="567d0-154">-Credential</span></span>

<span data-ttu-id="567d0-155">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="567d0-155">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="567d0-156">По умолчанию командлет использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="567d0-156">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="567d0-157">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="567d0-157">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="567d0-158">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="567d0-158">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="567d0-159">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="567d0-159">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="567d0-160">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="567d0-160">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-161">-FilePath</span><span class="sxs-lookup"><span data-stu-id="567d0-161">-FilePath</span></span>

<span data-ttu-id="567d0-162">Указывает необязательный путь и имя файла программы, выполняемой в процессе.</span><span class="sxs-lookup"><span data-stu-id="567d0-162">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="567d0-163">Введите имя исполняемого файла или документа, например `.txt` `.doc` файла или, связанного с программой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="567d0-163">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="567d0-164">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="567d0-164">This parameter is required.</span></span>

<span data-ttu-id="567d0-165">Если указано только имя файла, используйте параметр **WorkingDirectory** , чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="567d0-165">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-166">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="567d0-166">-LoadUserProfile</span></span>

<span data-ttu-id="567d0-167">Указывает, что этот командлет загружает профиль пользователя Windows, хранящийся в разделе `HKEY_USERS` реестра для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="567d0-167">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="567d0-168">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="567d0-168">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="567d0-169">Этот параметр не влияет на профили PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d0-169">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="567d0-170">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="567d0-170">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-171">-NoNewWindow</span><span class="sxs-lookup"><span data-stu-id="567d0-171">-NoNewWindow</span></span>

<span data-ttu-id="567d0-172">Предотвращает запуск процесса в новом окне.</span><span class="sxs-lookup"><span data-stu-id="567d0-172">Start the new process in the current console window.</span></span> <span data-ttu-id="567d0-173">По умолчанию в Windows PowerShell открывает новое окно.</span><span class="sxs-lookup"><span data-stu-id="567d0-173">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="567d0-174">В системах, отличных от Windows, новое окно терминала никогда не появляется.</span><span class="sxs-lookup"><span data-stu-id="567d0-174">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="567d0-175">Использовать параметры **NoNewWindow** и **WindowStyle** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="567d0-175">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="567d0-176">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="567d0-176">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-177">-PassThru</span><span class="sxs-lookup"><span data-stu-id="567d0-177">-PassThru</span></span>

<span data-ttu-id="567d0-178">Возвращает объект процесса для каждого запущенного командлетом процесса</span><span class="sxs-lookup"><span data-stu-id="567d0-178">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="567d0-179">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="567d0-179">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-180">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="567d0-180">-RedirectStandardError</span></span>

<span data-ttu-id="567d0-181">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-181">Specifies a file.</span></span> <span data-ttu-id="567d0-182">Этот командлет отправляет все ошибки, созданные процессом, в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-182">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="567d0-183">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="567d0-183">Enter the path and filename.</span></span> <span data-ttu-id="567d0-184">По умолчанию все ошибки отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="567d0-184">By default, the errors are displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-185">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="567d0-185">-RedirectStandardInput</span></span>

<span data-ttu-id="567d0-186">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-186">Specifies a file.</span></span> <span data-ttu-id="567d0-187">Этот командлет считывает входные данные из указанного файла.</span><span class="sxs-lookup"><span data-stu-id="567d0-187">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="567d0-188">Введите путь и имя входного файла.</span><span class="sxs-lookup"><span data-stu-id="567d0-188">Enter the path and filename of the input file.</span></span> <span data-ttu-id="567d0-189">По умолчанию процесс получает входные данные с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="567d0-189">By default, the process gets its input from the keyboard.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-190">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="567d0-190">-RedirectStandardOutput</span></span>

<span data-ttu-id="567d0-191">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-191">Specifies a file.</span></span> <span data-ttu-id="567d0-192">Этот командлет отправляет выходные данные, созданные процессом, в указанный вами файл.</span><span class="sxs-lookup"><span data-stu-id="567d0-192">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="567d0-193">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="567d0-193">Enter the path and filename.</span></span> <span data-ttu-id="567d0-194">По умолчанию выходные данные отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="567d0-194">By default, the output is displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-195">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="567d0-195">-UseNewEnvironment</span></span>

<span data-ttu-id="567d0-196">Указывает, что этот командлет использует новые переменные среды, заданные для процесса.</span><span class="sxs-lookup"><span data-stu-id="567d0-196">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="567d0-197">По умолчанию запущенный процесс выполняется с переменными среды, унаследованными от родительского процесса.</span><span class="sxs-lookup"><span data-stu-id="567d0-197">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-198">-Verb</span><span class="sxs-lookup"><span data-stu-id="567d0-198">-Verb</span></span>

<span data-ttu-id="567d0-199">Задает команду, используемую при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="567d0-199">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="567d0-200">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="567d0-200">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="567d0-201">В приведенной ниже таблице показаны команды, доступные для некоторых распространенных типов файлов.</span><span class="sxs-lookup"><span data-stu-id="567d0-201">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="567d0-202">Тип файла</span><span class="sxs-lookup"><span data-stu-id="567d0-202">File type</span></span> |                <span data-ttu-id="567d0-203">Команды</span><span class="sxs-lookup"><span data-stu-id="567d0-203">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="567d0-204">.cmd</span><span class="sxs-lookup"><span data-stu-id="567d0-204">.cmd</span></span>      | <span data-ttu-id="567d0-205">Правка, открытие, печать, Запуск от имени, выполняющийся</span><span class="sxs-lookup"><span data-stu-id="567d0-205">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="567d0-206">EXE</span><span class="sxs-lookup"><span data-stu-id="567d0-206">.exe</span></span>      | <span data-ttu-id="567d0-207">Open, RunAs, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="567d0-207">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="567d0-208">.txt</span><span class="sxs-lookup"><span data-stu-id="567d0-208">.txt</span></span>      | <span data-ttu-id="567d0-209">Открытие, печать, Принтто</span><span class="sxs-lookup"><span data-stu-id="567d0-209">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="567d0-210">.wav</span><span class="sxs-lookup"><span data-stu-id="567d0-210">.wav</span></span>      | <span data-ttu-id="567d0-211">Открыть, воспроизвести</span><span class="sxs-lookup"><span data-stu-id="567d0-211">Open, Play</span></span>                          |

<span data-ttu-id="567d0-212">Чтобы найти команды, которые можно использовать с файлом, выполняемым в процессе, используйте `New-Object` командлет, чтобы создать объект **System. Diagnostics. ProcessStartInfo** для файла.</span><span class="sxs-lookup"><span data-stu-id="567d0-212">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="567d0-213">Доступные команды находятся в свойстве **Verbs** объекта **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="567d0-213">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="567d0-214">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="567d0-214">For details, see the examples.</span></span>

<span data-ttu-id="567d0-215">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="567d0-215">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-216">-Wait</span><span class="sxs-lookup"><span data-stu-id="567d0-216">-Wait</span></span>

<span data-ttu-id="567d0-217">Указывает, что этот командлет ожидает завершения указанного процесса и его потомков, прежде чем принимать дополнительные входные данные.</span><span class="sxs-lookup"><span data-stu-id="567d0-217">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="567d0-218">Этот параметр подавляет командную строку или оставляет окно до завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="567d0-218">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-219">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="567d0-219">-WindowStyle</span></span>

<span data-ttu-id="567d0-220">Определяет состояние окна для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="567d0-220">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="567d0-221">Допустимые значения для этого параметра: **нормальный**, **скрытый**, **сведенный** и **развернутый**.</span><span class="sxs-lookup"><span data-stu-id="567d0-221">The acceptable values for this parameter are: **Normal**, **Hidden**, **Minimized**, and **Maximized**.</span></span> <span data-ttu-id="567d0-222">Значение по умолчанию — **Обычная**.</span><span class="sxs-lookup"><span data-stu-id="567d0-222">The default value is **Normal**.</span></span>

<span data-ttu-id="567d0-223">Использовать параметры **WindowStyle** и **NoNewWindow** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="567d0-223">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="567d0-224">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="567d0-224">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-225">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="567d0-225">-WorkingDirectory</span></span>

<span data-ttu-id="567d0-226">Указывает расположение, в котором должен начинаться новый процесс.</span><span class="sxs-lookup"><span data-stu-id="567d0-226">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="567d0-227">По умолчанию это расположение исполняемого файла или документа, который запускается.</span><span class="sxs-lookup"><span data-stu-id="567d0-227">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="567d0-228">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="567d0-228">Wildcards are not supported.</span></span> <span data-ttu-id="567d0-229">Имя пути не должно содержать символы, интерпретируемые как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="567d0-229">The path name must not contain characters that would be interpreted as wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-230">-Confirm</span><span class="sxs-lookup"><span data-stu-id="567d0-230">-Confirm</span></span>

<span data-ttu-id="567d0-231">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="567d0-231">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-232">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="567d0-232">-WhatIf</span></span>

<span data-ttu-id="567d0-233">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="567d0-233">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="567d0-234">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="567d0-234">The cmdlet is not run.</span></span>

<span data-ttu-id="567d0-235">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="567d0-235">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="567d0-236">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="567d0-236">CommonParameters</span></span>

<span data-ttu-id="567d0-237">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="567d0-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="567d0-238">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="567d0-238">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="567d0-239">Входные данные</span><span class="sxs-lookup"><span data-stu-id="567d0-239">INPUTS</span></span>

### <span data-ttu-id="567d0-240">None</span><span class="sxs-lookup"><span data-stu-id="567d0-240">None</span></span>

<span data-ttu-id="567d0-241">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="567d0-241">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="567d0-242">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="567d0-242">OUTPUTS</span></span>

### <span data-ttu-id="567d0-243">Нет, System. Диагностика. Process</span><span class="sxs-lookup"><span data-stu-id="567d0-243">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="567d0-244">Этот командлет создает объект **System. Diagnostics. Process** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="567d0-244">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="567d0-245">В противном случае командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="567d0-245">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="567d0-246">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="567d0-246">NOTES</span></span>

- <span data-ttu-id="567d0-247">Этот командлет реализуется с помощью метода **Start** класса **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="567d0-247">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="567d0-248">Дополнительные сведения об этом методе см. в разделе [метод Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="567d0-248">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="567d0-249">В Windows при использовании **усеневенвиронмент** новый процесс запускается только с переменными среды по умолчанию, определенными для области **компьютера** .</span><span class="sxs-lookup"><span data-stu-id="567d0-249">On Windows, when you use **UseNewEnvironment**, the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="567d0-250">Это влияет на то, что параметр `$env:USERNAME` имеет значение **System**.</span><span class="sxs-lookup"><span data-stu-id="567d0-250">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="567d0-251">Ни одна из переменных из **пользовательской** области не включена.</span><span class="sxs-lookup"><span data-stu-id="567d0-251">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="567d0-252">В Windows наиболее распространенным вариантом использования `Start-Process` является использование параметра **Wait** для блокировки хода выполнения до завершения нового процесса.</span><span class="sxs-lookup"><span data-stu-id="567d0-252">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="567d0-253">В системе, отличной от Windows, это редко требуется, так как поведение по умолчанию для приложений командной строки эквивалентно `Start-Process -Wait` .</span><span class="sxs-lookup"><span data-stu-id="567d0-253">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="567d0-254">При использовании `Start-Process` в системах, отличных от Windows, новое окно терминала никогда не появляется.</span><span class="sxs-lookup"><span data-stu-id="567d0-254">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="567d0-255">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="567d0-255">RELATED LINKS</span></span>

[<span data-ttu-id="567d0-256">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="567d0-256">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="567d0-257">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="567d0-257">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="567d0-258">Get-Process</span><span class="sxs-lookup"><span data-stu-id="567d0-258">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="567d0-259">Start-Service</span><span class="sxs-lookup"><span data-stu-id="567d0-259">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="567d0-260">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="567d0-260">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="567d0-261">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="567d0-261">Wait-Process</span></span>](Wait-Process.md)
