---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: 8967f68e23a7b5447ce32f698bfe0cf1c44b9c9e
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524713"
---
# <span data-ttu-id="7d15b-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="7d15b-103">Start-Process</span></span>

## <span data-ttu-id="7d15b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7d15b-104">SYNOPSIS</span></span>
<span data-ttu-id="7d15b-105">Запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d15b-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="7d15b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d15b-106">SYNTAX</span></span>

### <span data-ttu-id="7d15b-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7d15b-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7d15b-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="7d15b-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="7d15b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7d15b-109">DESCRIPTION</span></span>

<span data-ttu-id="7d15b-110">`Start-Process`Командлет запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d15b-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="7d15b-111">По умолчанию `Start-Process` создает новый процесс, который наследует все переменные среды, определенные в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="7d15b-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="7d15b-112">Чтобы указать программу, выполняемую в процессе, введите исполняемый файл или файл скрипта, либо файл, который может быть открыт с помощью имеющейся на компьютере программы.</span><span class="sxs-lookup"><span data-stu-id="7d15b-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="7d15b-113">Если указан неисполняемый файл, `Start-Process` программа запускает программу, связанную с файлом, аналогично `Invoke-Item` командлету.</span><span class="sxs-lookup"><span data-stu-id="7d15b-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="7d15b-114">Параметры можно использовать `Start-Process` для указания параметров, таких как загрузка профиля пользователя, запуск процесса в новом окне или использование альтернативных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7d15b-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="7d15b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="7d15b-115">EXAMPLES</span></span>

### <span data-ttu-id="7d15b-116">Пример 1. Запуск процесса, использующего значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7d15b-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="7d15b-117">В этом примере запускается процесс, который использует `Sort.exe` файл в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="7d15b-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="7d15b-118">Команда использует все значения по умолчанию, включая стиль окна по умолчанию, рабочую папку и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="7d15b-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="7d15b-119">Пример 2. Печать текстового файла</span><span class="sxs-lookup"><span data-stu-id="7d15b-119">Example 2: Print a text file</span></span>

<span data-ttu-id="7d15b-120">В этом примере запускается процесс, который выводит `C:\PS-Test\MyFile.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="7d15b-121">Пример 3. Запуск процесса для сортировки элементов в новый файл</span><span class="sxs-lookup"><span data-stu-id="7d15b-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="7d15b-122">В этом примере запускается процесс, который сортирует элементы в `Testsort.txt` файле и возвращает отсортированные элементы в `Sorted.txt` файлах.</span><span class="sxs-lookup"><span data-stu-id="7d15b-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="7d15b-123">Все ошибки записываются в `SortError.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="7d15b-124">Параметр **усеневенвиронмент** указывает, что процесс выполняется с собственными переменными среды.</span><span class="sxs-lookup"><span data-stu-id="7d15b-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="7d15b-125">Пример 4. Запуск процесса в развернутом окне</span><span class="sxs-lookup"><span data-stu-id="7d15b-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="7d15b-126">В этом примере запускается `Notepad.exe` процесс.</span><span class="sxs-lookup"><span data-stu-id="7d15b-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="7d15b-127">Окно разворачивается во весь экран и удерживается до завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="7d15b-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="7d15b-128">Пример 5. Запуск PowerShell от имени администратора</span><span class="sxs-lookup"><span data-stu-id="7d15b-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="7d15b-129">В этом примере запускается PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="7d15b-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="7d15b-130">Пример 6. Использование различных команд для запуска процесса</span><span class="sxs-lookup"><span data-stu-id="7d15b-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="7d15b-131">В этом примере показано, как найти команды, которые можно использовать при запуске процесса.</span><span class="sxs-lookup"><span data-stu-id="7d15b-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="7d15b-132">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="7d15b-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="7d15b-133">В примере используется `New-Object` для создания объекта **System. Diagnostics. ProcessStartInfo** для **PowerShell.exe** — файла, который выполняется в процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d15b-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="7d15b-134">Свойство **Verbs** объекта **ProcessStartInfo** показывает, что можно использовать команды **Open** и **runas** с `PowerShell.exe` или с любым процессом, запускающим `.exe` файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="7d15b-135">Пример 7. Указание аргументов для процесса</span><span class="sxs-lookup"><span data-stu-id="7d15b-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="7d15b-136">Обе команды запускают интерпретатор команд Windows, выполняя `dir` команду в `Program Files` папке.</span><span class="sxs-lookup"><span data-stu-id="7d15b-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="7d15b-137">Поскольку это переключка содержит пробел, значение должно заключаться в экранированные кавычки.</span><span class="sxs-lookup"><span data-stu-id="7d15b-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="7d15b-138">Обратите внимание, что первая команда указывает строку как **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="7d15b-138">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="7d15b-139">Вторая команда является массивом строк.</span><span class="sxs-lookup"><span data-stu-id="7d15b-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

### <span data-ttu-id="7d15b-140">Пример 8. Создание отсоединенного процесса в Linux</span><span class="sxs-lookup"><span data-stu-id="7d15b-140">Example 8: Create a detached process on Linux</span></span>

<span data-ttu-id="7d15b-141">В Windows `Start-Process` создает независимый процесс, который остается запущенным независимо от запуска оболочки.</span><span class="sxs-lookup"><span data-stu-id="7d15b-141">On Windows, `Start-Process` creates an independent process that remains running independently of the launching shell.</span></span> <span data-ttu-id="7d15b-142">На платформах, отличных от Windows, вновь запущенный процесс прикрепляется к запущенной оболочке.</span><span class="sxs-lookup"><span data-stu-id="7d15b-142">On non-Windows platforms, the newly started process is attached to the shell that launched.</span></span> <span data-ttu-id="7d15b-143">Если закрывается Запуск оболочки, дочерний процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="7d15b-143">If the launching shell is closed, the child process is terminated.</span></span>

<span data-ttu-id="7d15b-144">Во избежание завершения дочернего процесса на платформах, подобных Unix, можно сочетать `Start-Process` с `nohup` .</span><span class="sxs-lookup"><span data-stu-id="7d15b-144">To avoid terminating the child process on Unix-like platforms, you can combine `Start-Process` with `nohup`.</span></span> <span data-ttu-id="7d15b-145">В следующем примере запускается фоновый экземпляр PowerShell в Linux, который остается активным даже после закрытия сеанса запуска.</span><span class="sxs-lookup"><span data-stu-id="7d15b-145">The following example launches a background instance of PowerShell on Linux that stays alive even after you close the launching session.</span></span> <span data-ttu-id="7d15b-146">`nohup`Команда собирает выходные данные в файле `nohup.out` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7d15b-146">The `nohup` command collects output in file `nohup.out` in the current directory.</span></span>

```powershell
# Runs for 2 minutes and appends output to ./nohup.out
Start-Process nohup 'pwsh -noprofile -c "1..120 | % { Write-Host . -NoNewline; sleep 1 }"'
```

<span data-ttu-id="7d15b-147">В этом примере `Start-Process` выполняет `nohup` команду Linux, которая запускается `pwsh` как отсоединенный процесс.</span><span class="sxs-lookup"><span data-stu-id="7d15b-147">In this example, `Start-Process` is running the Linux `nohup` command, which launches `pwsh` as a detached process.</span></span> <span data-ttu-id="7d15b-148">Дополнительные сведения см. на справочной странице [нохуп](https://linux.die.net/man/1/nohup).</span><span class="sxs-lookup"><span data-stu-id="7d15b-148">For more information, see the man page for [nohup](https://linux.die.net/man/1/nohup).</span></span>

## <span data-ttu-id="7d15b-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d15b-149">PARAMETERS</span></span>

### <span data-ttu-id="7d15b-150">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="7d15b-150">-ArgumentList</span></span>

<span data-ttu-id="7d15b-151">Указывает параметры или значения параметров, которые следует использовать при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="7d15b-151">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="7d15b-152">Аргументы можно принимать как одну строку с аргументами, разделенными пробелами, или как массив строк, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="7d15b-152">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="7d15b-153">Если параметры или значения параметров содержат пробел, их необходимо заключить в escape-символы, заключенные в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="7d15b-153">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="7d15b-154">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="7d15b-154">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="7d15b-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="7d15b-155">-Credential</span></span>

<span data-ttu-id="7d15b-156">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="7d15b-156">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="7d15b-157">По умолчанию командлет использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d15b-157">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="7d15b-158">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="7d15b-158">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="7d15b-159">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="7d15b-159">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="7d15b-160">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="7d15b-160">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="7d15b-161">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="7d15b-161">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="7d15b-162">-FilePath</span><span class="sxs-lookup"><span data-stu-id="7d15b-162">-FilePath</span></span>

<span data-ttu-id="7d15b-163">Указывает необязательный путь и имя файла программы, выполняемой в процессе.</span><span class="sxs-lookup"><span data-stu-id="7d15b-163">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="7d15b-164">Введите имя исполняемого файла или документа, например `.txt` `.doc` файла или, связанного с программой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d15b-164">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="7d15b-165">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="7d15b-165">This parameter is required.</span></span>

<span data-ttu-id="7d15b-166">Если указано только имя файла, используйте параметр **WorkingDirectory** , чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="7d15b-166">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

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

### <span data-ttu-id="7d15b-167">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="7d15b-167">-LoadUserProfile</span></span>

<span data-ttu-id="7d15b-168">Указывает, что этот командлет загружает профиль пользователя Windows, хранящийся в разделе `HKEY_USERS` реестра для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d15b-168">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="7d15b-169">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="7d15b-169">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="7d15b-170">Этот параметр не влияет на профили PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d15b-170">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="7d15b-171">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7d15b-171">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

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

### <span data-ttu-id="7d15b-172">-NoNewWindow</span><span class="sxs-lookup"><span data-stu-id="7d15b-172">-NoNewWindow</span></span>

<span data-ttu-id="7d15b-173">Предотвращает запуск процесса в новом окне.</span><span class="sxs-lookup"><span data-stu-id="7d15b-173">Start the new process in the current console window.</span></span> <span data-ttu-id="7d15b-174">По умолчанию в Windows PowerShell открывает новое окно.</span><span class="sxs-lookup"><span data-stu-id="7d15b-174">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="7d15b-175">В системах, отличных от Windows, новое окно терминала никогда не появляется.</span><span class="sxs-lookup"><span data-stu-id="7d15b-175">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="7d15b-176">Использовать параметры **NoNewWindow** и **WindowStyle** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="7d15b-176">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="7d15b-177">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="7d15b-177">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="7d15b-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7d15b-178">-PassThru</span></span>

<span data-ttu-id="7d15b-179">Возвращает объект процесса для каждого запущенного командлетом процесса</span><span class="sxs-lookup"><span data-stu-id="7d15b-179">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="7d15b-180">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="7d15b-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7d15b-181">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="7d15b-181">-RedirectStandardError</span></span>

<span data-ttu-id="7d15b-182">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-182">Specifies a file.</span></span> <span data-ttu-id="7d15b-183">Этот командлет отправляет все ошибки, созданные процессом, в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-183">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="7d15b-184">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="7d15b-184">Enter the path and filename.</span></span> <span data-ttu-id="7d15b-185">По умолчанию все ошибки отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="7d15b-185">By default, the errors are displayed in the console.</span></span>

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

### <span data-ttu-id="7d15b-186">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="7d15b-186">-RedirectStandardInput</span></span>

<span data-ttu-id="7d15b-187">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-187">Specifies a file.</span></span> <span data-ttu-id="7d15b-188">Этот командлет считывает входные данные из указанного файла.</span><span class="sxs-lookup"><span data-stu-id="7d15b-188">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="7d15b-189">Введите путь и имя входного файла.</span><span class="sxs-lookup"><span data-stu-id="7d15b-189">Enter the path and filename of the input file.</span></span> <span data-ttu-id="7d15b-190">По умолчанию процесс получает входные данные с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="7d15b-190">By default, the process gets its input from the keyboard.</span></span>

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

### <span data-ttu-id="7d15b-191">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="7d15b-191">-RedirectStandardOutput</span></span>

<span data-ttu-id="7d15b-192">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-192">Specifies a file.</span></span> <span data-ttu-id="7d15b-193">Этот командлет отправляет выходные данные, созданные процессом, в указанный вами файл.</span><span class="sxs-lookup"><span data-stu-id="7d15b-193">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="7d15b-194">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="7d15b-194">Enter the path and filename.</span></span> <span data-ttu-id="7d15b-195">По умолчанию выходные данные отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="7d15b-195">By default, the output is displayed in the console.</span></span>

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

### <span data-ttu-id="7d15b-196">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="7d15b-196">-UseNewEnvironment</span></span>

<span data-ttu-id="7d15b-197">Указывает, что этот командлет использует новые переменные среды, заданные для процесса.</span><span class="sxs-lookup"><span data-stu-id="7d15b-197">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="7d15b-198">По умолчанию запущенный процесс выполняется с переменными среды, унаследованными от родительского процесса.</span><span class="sxs-lookup"><span data-stu-id="7d15b-198">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

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

### <span data-ttu-id="7d15b-199">-Verb</span><span class="sxs-lookup"><span data-stu-id="7d15b-199">-Verb</span></span>

<span data-ttu-id="7d15b-200">Задает команду, используемую при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="7d15b-200">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="7d15b-201">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="7d15b-201">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="7d15b-202">В приведенной ниже таблице показаны команды, доступные для некоторых распространенных типов файлов.</span><span class="sxs-lookup"><span data-stu-id="7d15b-202">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="7d15b-203">Тип файла</span><span class="sxs-lookup"><span data-stu-id="7d15b-203">File type</span></span> |                <span data-ttu-id="7d15b-204">Команды</span><span class="sxs-lookup"><span data-stu-id="7d15b-204">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="7d15b-205">.cmd</span><span class="sxs-lookup"><span data-stu-id="7d15b-205">.cmd</span></span>      | <span data-ttu-id="7d15b-206">Правка, открытие, печать, Запуск от имени, выполняющийся</span><span class="sxs-lookup"><span data-stu-id="7d15b-206">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="7d15b-207">EXE</span><span class="sxs-lookup"><span data-stu-id="7d15b-207">.exe</span></span>      | <span data-ttu-id="7d15b-208">Open, RunAs, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="7d15b-208">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="7d15b-209">.txt</span><span class="sxs-lookup"><span data-stu-id="7d15b-209">.txt</span></span>      | <span data-ttu-id="7d15b-210">Открытие, печать, Принтто</span><span class="sxs-lookup"><span data-stu-id="7d15b-210">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="7d15b-211">.wav</span><span class="sxs-lookup"><span data-stu-id="7d15b-211">.wav</span></span>      | <span data-ttu-id="7d15b-212">Открыть, воспроизвести</span><span class="sxs-lookup"><span data-stu-id="7d15b-212">Open, Play</span></span>                          |

<span data-ttu-id="7d15b-213">Чтобы найти команды, которые можно использовать с файлом, выполняемым в процессе, используйте `New-Object` командлет, чтобы создать объект **System. Diagnostics. ProcessStartInfo** для файла.</span><span class="sxs-lookup"><span data-stu-id="7d15b-213">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="7d15b-214">Доступные команды находятся в свойстве **Verbs** объекта **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="7d15b-214">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="7d15b-215">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="7d15b-215">For details, see the examples.</span></span>

<span data-ttu-id="7d15b-216">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="7d15b-216">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="7d15b-217">-Wait</span><span class="sxs-lookup"><span data-stu-id="7d15b-217">-Wait</span></span>

<span data-ttu-id="7d15b-218">Указывает, что этот командлет ожидает завершения указанного процесса и его потомков, прежде чем принимать дополнительные входные данные.</span><span class="sxs-lookup"><span data-stu-id="7d15b-218">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="7d15b-219">Этот параметр подавляет командную строку или оставляет окно до завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="7d15b-219">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="7d15b-220">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="7d15b-220">-WindowStyle</span></span>

<span data-ttu-id="7d15b-221">Определяет состояние окна для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="7d15b-221">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="7d15b-222">Допустимые значения для этого параметра: **нормальный** , **скрытый** , **сведенный** и **развернутый**.</span><span class="sxs-lookup"><span data-stu-id="7d15b-222">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized**.</span></span> <span data-ttu-id="7d15b-223">Значение по умолчанию — **Обычная**.</span><span class="sxs-lookup"><span data-stu-id="7d15b-223">The default value is **Normal**.</span></span>

<span data-ttu-id="7d15b-224">Использовать параметры **WindowStyle** и **NoNewWindow** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="7d15b-224">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="7d15b-225">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="7d15b-225">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="7d15b-226">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="7d15b-226">-WorkingDirectory</span></span>

<span data-ttu-id="7d15b-227">Указывает расположение, в котором должен начинаться новый процесс.</span><span class="sxs-lookup"><span data-stu-id="7d15b-227">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="7d15b-228">По умолчанию это расположение исполняемого файла или документа, который запускается.</span><span class="sxs-lookup"><span data-stu-id="7d15b-228">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="7d15b-229">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7d15b-229">Wildcards are not supported.</span></span> <span data-ttu-id="7d15b-230">Имя пути не должно содержать символы, интерпретируемые как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7d15b-230">The path name must not contain characters that would be interpreted as wildcards.</span></span>

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

### <span data-ttu-id="7d15b-231">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7d15b-231">-Confirm</span></span>

<span data-ttu-id="7d15b-232">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="7d15b-232">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7d15b-233">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7d15b-233">-WhatIf</span></span>

<span data-ttu-id="7d15b-234">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="7d15b-234">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7d15b-235">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7d15b-235">The cmdlet is not run.</span></span>

<span data-ttu-id="7d15b-236">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="7d15b-236">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="7d15b-237">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7d15b-237">CommonParameters</span></span>

<span data-ttu-id="7d15b-238">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7d15b-238">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d15b-239">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7d15b-239">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7d15b-240">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7d15b-240">INPUTS</span></span>

### <span data-ttu-id="7d15b-241">None</span><span class="sxs-lookup"><span data-stu-id="7d15b-241">None</span></span>

<span data-ttu-id="7d15b-242">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="7d15b-242">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7d15b-243">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7d15b-243">OUTPUTS</span></span>

### <span data-ttu-id="7d15b-244">Нет, System. Диагностика. Process</span><span class="sxs-lookup"><span data-stu-id="7d15b-244">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="7d15b-245">Этот командлет создает объект **System. Diagnostics. Process** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="7d15b-245">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="7d15b-246">В противном случае командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7d15b-246">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="7d15b-247">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7d15b-247">NOTES</span></span>

- <span data-ttu-id="7d15b-248">Этот командлет реализуется с помощью метода **Start** класса **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="7d15b-248">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="7d15b-249">Дополнительные сведения об этом методе см. в разделе [метод Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="7d15b-249">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="7d15b-250">В Windows при использовании **усеневенвиронмент** новый процесс запускается только с переменными среды по умолчанию, определенными для области **компьютера** .</span><span class="sxs-lookup"><span data-stu-id="7d15b-250">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="7d15b-251">Это влияет на то, что параметр `$env:USERNAME` имеет значение **System**.</span><span class="sxs-lookup"><span data-stu-id="7d15b-251">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="7d15b-252">Ни одна из переменных из **пользовательской** области не включена.</span><span class="sxs-lookup"><span data-stu-id="7d15b-252">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="7d15b-253">В Windows наиболее распространенным вариантом использования `Start-Process` является использование параметра **Wait** для блокировки хода выполнения до завершения нового процесса.</span><span class="sxs-lookup"><span data-stu-id="7d15b-253">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="7d15b-254">В системе, отличной от Windows, это редко требуется, так как поведение по умолчанию для приложений командной строки эквивалентно `Start-Process -Wait` .</span><span class="sxs-lookup"><span data-stu-id="7d15b-254">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="7d15b-255">При использовании `Start-Process` в системах, отличных от Windows, новое окно терминала никогда не появляется.</span><span class="sxs-lookup"><span data-stu-id="7d15b-255">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="7d15b-256">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7d15b-256">RELATED LINKS</span></span>

[<span data-ttu-id="7d15b-257">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="7d15b-257">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="7d15b-258">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="7d15b-258">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="7d15b-259">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7d15b-259">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="7d15b-260">Start-Service</span><span class="sxs-lookup"><span data-stu-id="7d15b-260">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="7d15b-261">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="7d15b-261">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="7d15b-262">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="7d15b-262">Wait-Process</span></span>](Wait-Process.md)
