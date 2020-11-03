---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: a221c6126bbbf22dffb493828f759bcbd4cfe759
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "93230194"
---
# <span data-ttu-id="c43e2-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="c43e2-103">Start-Process</span></span>

## <span data-ttu-id="c43e2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c43e2-104">SYNOPSIS</span></span>
<span data-ttu-id="c43e2-105">Запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c43e2-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="c43e2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c43e2-106">SYNTAX</span></span>

### <span data-ttu-id="c43e2-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c43e2-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c43e2-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="c43e2-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="c43e2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c43e2-109">DESCRIPTION</span></span>

<span data-ttu-id="c43e2-110">`Start-Process`Командлет запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c43e2-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="c43e2-111">По умолчанию `Start-Process` создает новый процесс, который наследует все переменные среды, определенные в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="c43e2-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="c43e2-112">Чтобы указать программу, выполняемую в процессе, введите исполняемый файл или файл скрипта, либо файл, который может быть открыт с помощью имеющейся на компьютере программы.</span><span class="sxs-lookup"><span data-stu-id="c43e2-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="c43e2-113">Если указан неисполняемый файл, `Start-Process` программа запускает программу, связанную с файлом, аналогично `Invoke-Item` командлету.</span><span class="sxs-lookup"><span data-stu-id="c43e2-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="c43e2-114">Параметры можно использовать `Start-Process` для указания параметров, таких как загрузка профиля пользователя, запуск процесса в новом окне или использование альтернативных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c43e2-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="c43e2-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="c43e2-115">EXAMPLES</span></span>

### <span data-ttu-id="c43e2-116">Пример 1. Запуск процесса, использующего значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c43e2-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="c43e2-117">В этом примере запускается процесс, который использует `Sort.exe` файл в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="c43e2-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="c43e2-118">Команда использует все значения по умолчанию, включая стиль окна по умолчанию, рабочую папку и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c43e2-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="c43e2-119">Пример 2. Печать текстового файла</span><span class="sxs-lookup"><span data-stu-id="c43e2-119">Example 2: Print a text file</span></span>

<span data-ttu-id="c43e2-120">В этом примере запускается процесс, который выводит `C:\PS-Test\MyFile.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="c43e2-121">Пример 3. Запуск процесса для сортировки элементов в новый файл</span><span class="sxs-lookup"><span data-stu-id="c43e2-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="c43e2-122">В этом примере запускается процесс, который сортирует элементы в `Testsort.txt` файле и возвращает отсортированные элементы в `Sorted.txt` файлах.</span><span class="sxs-lookup"><span data-stu-id="c43e2-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="c43e2-123">Все ошибки записываются в `SortError.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="c43e2-124">Параметр **усеневенвиронмент** указывает, что процесс выполняется с собственными переменными среды.</span><span class="sxs-lookup"><span data-stu-id="c43e2-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="c43e2-125">Пример 4. Запуск процесса в развернутом окне</span><span class="sxs-lookup"><span data-stu-id="c43e2-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="c43e2-126">В этом примере запускается `Notepad.exe` процесс.</span><span class="sxs-lookup"><span data-stu-id="c43e2-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="c43e2-127">Окно разворачивается во весь экран и удерживается до завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="c43e2-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="c43e2-128">Пример 5. Запуск PowerShell от имени администратора</span><span class="sxs-lookup"><span data-stu-id="c43e2-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="c43e2-129">В этом примере запускается PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="c43e2-130">Пример 6. Использование различных команд для запуска процесса</span><span class="sxs-lookup"><span data-stu-id="c43e2-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="c43e2-131">В этом примере показано, как найти команды, которые можно использовать при запуске процесса.</span><span class="sxs-lookup"><span data-stu-id="c43e2-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="c43e2-132">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="c43e2-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="c43e2-133">В примере используется `New-Object` для создания объекта **System. Diagnostics. ProcessStartInfo** для **PowerShell.exe** — файла, который выполняется в процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c43e2-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="c43e2-134">Свойство **Verbs** объекта **ProcessStartInfo** показывает, что можно использовать команды **Open** и **runas** с `PowerShell.exe` или с любым процессом, запускающим `.exe` файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="c43e2-135">Пример 7. Указание аргументов для процесса</span><span class="sxs-lookup"><span data-stu-id="c43e2-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="c43e2-136">Обе команды запускают интерпретатор команд Windows, выполняя `dir` команду в `Program Files` папке.</span><span class="sxs-lookup"><span data-stu-id="c43e2-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="c43e2-137">Поскольку это переключка содержит пробел, значение должно заключаться в экранированные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c43e2-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="c43e2-138">Обратите внимание, что первая команда указывает строку как **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-138">Note that the first command specifies a string as **ArgumentList** .</span></span> <span data-ttu-id="c43e2-139">Вторая команда является массивом строк.</span><span class="sxs-lookup"><span data-stu-id="c43e2-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="c43e2-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c43e2-140">PARAMETERS</span></span>

### <span data-ttu-id="c43e2-141">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="c43e2-141">-ArgumentList</span></span>

<span data-ttu-id="c43e2-142">Указывает параметры или значения параметров, которые следует использовать при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="c43e2-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="c43e2-143">Аргументы можно принимать как одну строку с аргументами, разделенными пробелами, или как массив строк, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="c43e2-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="c43e2-144">Если параметры или значения параметров содержат пробел, их необходимо заключить в escape-символы, заключенные в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c43e2-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="c43e2-145">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c43e2-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="c43e2-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="c43e2-146">-Credential</span></span>

<span data-ttu-id="c43e2-147">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="c43e2-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="c43e2-148">По умолчанию командлет использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c43e2-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="c43e2-149">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="c43e2-149">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="c43e2-150">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="c43e2-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="c43e2-151">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="c43e2-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="c43e2-152">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="c43e2-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="c43e2-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="c43e2-153">-FilePath</span></span>

<span data-ttu-id="c43e2-154">Указывает необязательный путь и имя файла программы, выполняемой в процессе.</span><span class="sxs-lookup"><span data-stu-id="c43e2-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="c43e2-155">Введите имя исполняемого файла или документа, например `.txt` `.doc` файла или, связанного с программой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c43e2-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="c43e2-156">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="c43e2-156">This parameter is required.</span></span>

<span data-ttu-id="c43e2-157">Если указано только имя файла, используйте параметр **WorkingDirectory** , чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="c43e2-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

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

### <span data-ttu-id="c43e2-158">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="c43e2-158">-LoadUserProfile</span></span>

<span data-ttu-id="c43e2-159">Указывает, что этот командлет загружает профиль пользователя Windows, хранящийся в разделе `HKEY_USERS` реестра для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c43e2-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="c43e2-160">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="c43e2-160">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="c43e2-161">Этот параметр не влияет на профили PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c43e2-161">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="c43e2-162">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c43e2-162">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

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

### <span data-ttu-id="c43e2-163">-NoNewWindow</span><span class="sxs-lookup"><span data-stu-id="c43e2-163">-NoNewWindow</span></span>

<span data-ttu-id="c43e2-164">Предотвращает запуск процесса в новом окне.</span><span class="sxs-lookup"><span data-stu-id="c43e2-164">Start the new process in the current console window.</span></span> <span data-ttu-id="c43e2-165">По умолчанию в Windows PowerShell открывает новое окно.</span><span class="sxs-lookup"><span data-stu-id="c43e2-165">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="c43e2-166">В системах, отличных от Windows, новое окно терминала никогда не появляется.</span><span class="sxs-lookup"><span data-stu-id="c43e2-166">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="c43e2-167">Использовать параметры **NoNewWindow** и **WindowStyle** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="c43e2-167">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="c43e2-168">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="c43e2-168">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="c43e2-169">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c43e2-169">-PassThru</span></span>

<span data-ttu-id="c43e2-170">Возвращает объект процесса для каждого запущенного командлетом процесса</span><span class="sxs-lookup"><span data-stu-id="c43e2-170">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="c43e2-171">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c43e2-171">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c43e2-172">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="c43e2-172">-RedirectStandardError</span></span>

<span data-ttu-id="c43e2-173">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-173">Specifies a file.</span></span> <span data-ttu-id="c43e2-174">Этот командлет отправляет все ошибки, созданные процессом, в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-174">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="c43e2-175">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c43e2-175">Enter the path and filename.</span></span> <span data-ttu-id="c43e2-176">По умолчанию все ошибки отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="c43e2-176">By default, the errors are displayed in the console.</span></span>

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

### <span data-ttu-id="c43e2-177">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="c43e2-177">-RedirectStandardInput</span></span>

<span data-ttu-id="c43e2-178">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-178">Specifies a file.</span></span> <span data-ttu-id="c43e2-179">Этот командлет считывает входные данные из указанного файла.</span><span class="sxs-lookup"><span data-stu-id="c43e2-179">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="c43e2-180">Введите путь и имя входного файла.</span><span class="sxs-lookup"><span data-stu-id="c43e2-180">Enter the path and filename of the input file.</span></span> <span data-ttu-id="c43e2-181">По умолчанию процесс получает входные данные с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="c43e2-181">By default, the process gets its input from the keyboard.</span></span>

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

### <span data-ttu-id="c43e2-182">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="c43e2-182">-RedirectStandardOutput</span></span>

<span data-ttu-id="c43e2-183">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-183">Specifies a file.</span></span> <span data-ttu-id="c43e2-184">Этот командлет отправляет выходные данные, созданные процессом, в указанный вами файл.</span><span class="sxs-lookup"><span data-stu-id="c43e2-184">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="c43e2-185">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c43e2-185">Enter the path and filename.</span></span> <span data-ttu-id="c43e2-186">По умолчанию выходные данные отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="c43e2-186">By default, the output is displayed in the console.</span></span>

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

### <span data-ttu-id="c43e2-187">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="c43e2-187">-UseNewEnvironment</span></span>

<span data-ttu-id="c43e2-188">Указывает, что этот командлет использует новые переменные среды, заданные для процесса.</span><span class="sxs-lookup"><span data-stu-id="c43e2-188">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="c43e2-189">По умолчанию запущенный процесс выполняется с переменными среды, унаследованными от родительского процесса.</span><span class="sxs-lookup"><span data-stu-id="c43e2-189">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

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

### <span data-ttu-id="c43e2-190">-Verb</span><span class="sxs-lookup"><span data-stu-id="c43e2-190">-Verb</span></span>

<span data-ttu-id="c43e2-191">Задает команду, используемую при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="c43e2-191">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="c43e2-192">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="c43e2-192">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="c43e2-193">В приведенной ниже таблице показаны команды, доступные для некоторых распространенных типов файлов.</span><span class="sxs-lookup"><span data-stu-id="c43e2-193">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="c43e2-194">Тип файла</span><span class="sxs-lookup"><span data-stu-id="c43e2-194">File type</span></span> |                <span data-ttu-id="c43e2-195">Команды</span><span class="sxs-lookup"><span data-stu-id="c43e2-195">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="c43e2-196">.cmd</span><span class="sxs-lookup"><span data-stu-id="c43e2-196">.cmd</span></span>      | <span data-ttu-id="c43e2-197">Правка, открытие, печать, Запуск от имени, выполняющийся</span><span class="sxs-lookup"><span data-stu-id="c43e2-197">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="c43e2-198">EXE</span><span class="sxs-lookup"><span data-stu-id="c43e2-198">.exe</span></span>      | <span data-ttu-id="c43e2-199">Open, RunAs, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="c43e2-199">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="c43e2-200">.txt</span><span class="sxs-lookup"><span data-stu-id="c43e2-200">.txt</span></span>      | <span data-ttu-id="c43e2-201">Открытие, печать, Принтто</span><span class="sxs-lookup"><span data-stu-id="c43e2-201">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="c43e2-202">.wav</span><span class="sxs-lookup"><span data-stu-id="c43e2-202">.wav</span></span>      | <span data-ttu-id="c43e2-203">Открыть, воспроизвести</span><span class="sxs-lookup"><span data-stu-id="c43e2-203">Open, Play</span></span>                          |

<span data-ttu-id="c43e2-204">Чтобы найти команды, которые можно использовать с файлом, выполняемым в процессе, используйте `New-Object` командлет, чтобы создать объект **System. Diagnostics. ProcessStartInfo** для файла.</span><span class="sxs-lookup"><span data-stu-id="c43e2-204">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="c43e2-205">Доступные команды находятся в свойстве **Verbs** объекта **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-205">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="c43e2-206">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="c43e2-206">For details, see the examples.</span></span>

<span data-ttu-id="c43e2-207">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="c43e2-207">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="c43e2-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="c43e2-208">-Wait</span></span>

<span data-ttu-id="c43e2-209">Указывает, что этот командлет ожидает завершения указанного процесса и его потомков, прежде чем принимать дополнительные входные данные.</span><span class="sxs-lookup"><span data-stu-id="c43e2-209">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="c43e2-210">Этот параметр подавляет командную строку или оставляет окно до завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="c43e2-210">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="c43e2-211">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="c43e2-211">-WindowStyle</span></span>

<span data-ttu-id="c43e2-212">Определяет состояние окна для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="c43e2-212">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="c43e2-213">Допустимые значения для этого параметра: **нормальный** , **скрытый** , **сведенный** и **развернутый** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-213">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized** .</span></span> <span data-ttu-id="c43e2-214">Значение по умолчанию — **Обычная** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-214">The default value is **Normal** .</span></span>

<span data-ttu-id="c43e2-215">Использовать параметры **WindowStyle** и **NoNewWindow** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="c43e2-215">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="c43e2-216">Параметр не применяется для систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="c43e2-216">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="c43e2-217">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="c43e2-217">-WorkingDirectory</span></span>

<span data-ttu-id="c43e2-218">Указывает расположение, в котором должен начинаться новый процесс.</span><span class="sxs-lookup"><span data-stu-id="c43e2-218">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="c43e2-219">По умолчанию это расположение исполняемого файла или документа, который запускается.</span><span class="sxs-lookup"><span data-stu-id="c43e2-219">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="c43e2-220">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c43e2-220">Wildcards are not supported.</span></span> <span data-ttu-id="c43e2-221">Имя пути не должно содержать символы, интерпретируемые как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c43e2-221">The path name must not contain characters that would be interpreted as wildcards.</span></span>

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

### <span data-ttu-id="c43e2-222">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c43e2-222">-Confirm</span></span>

<span data-ttu-id="c43e2-223">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c43e2-223">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c43e2-224">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c43e2-224">-WhatIf</span></span>

<span data-ttu-id="c43e2-225">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c43e2-225">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c43e2-226">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c43e2-226">The cmdlet is not run.</span></span>

<span data-ttu-id="c43e2-227">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="c43e2-227">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="c43e2-228">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c43e2-228">CommonParameters</span></span>

<span data-ttu-id="c43e2-229">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c43e2-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c43e2-230">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c43e2-230">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c43e2-231">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c43e2-231">INPUTS</span></span>

### <span data-ttu-id="c43e2-232">Нет</span><span class="sxs-lookup"><span data-stu-id="c43e2-232">None</span></span>

<span data-ttu-id="c43e2-233">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="c43e2-233">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c43e2-234">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c43e2-234">OUTPUTS</span></span>

### <span data-ttu-id="c43e2-235">Нет, System. Диагностика. Process</span><span class="sxs-lookup"><span data-stu-id="c43e2-235">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="c43e2-236">Этот командлет создает объект **System. Diagnostics. Process** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-236">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="c43e2-237">В противном случае командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c43e2-237">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="c43e2-238">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c43e2-238">NOTES</span></span>

- <span data-ttu-id="c43e2-239">Этот командлет реализуется с помощью метода **Start** класса **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-239">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="c43e2-240">Дополнительные сведения об этом методе см. в разделе [метод Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="c43e2-240">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="c43e2-241">В Windows при использовании **усеневенвиронмент** новый процесс запускается только с переменными среды по умолчанию, определенными для области **компьютера** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-241">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="c43e2-242">Это влияет на то, что параметр `$env:USERNAME` имеет значение **System** .</span><span class="sxs-lookup"><span data-stu-id="c43e2-242">This has the side affect that the `$env:USERNAME` is set to **SYSTEM** .</span></span> <span data-ttu-id="c43e2-243">Ни одна из переменных из **пользовательской** области не включена.</span><span class="sxs-lookup"><span data-stu-id="c43e2-243">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="c43e2-244">В Windows наиболее распространенным вариантом использования `Start-Process` является использование параметра **Wait** для блокировки хода выполнения до завершения нового процесса.</span><span class="sxs-lookup"><span data-stu-id="c43e2-244">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="c43e2-245">В системе, отличной от Windows, это редко требуется, так как поведение по умолчанию для приложений командной строки эквивалентно `Start-Process -Wait` .</span><span class="sxs-lookup"><span data-stu-id="c43e2-245">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="c43e2-246">При использовании `Start-Process` в системах, отличных от Windows, новое окно терминала никогда не появляется.</span><span class="sxs-lookup"><span data-stu-id="c43e2-246">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="c43e2-247">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c43e2-247">RELATED LINKS</span></span>

[<span data-ttu-id="c43e2-248">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="c43e2-248">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="c43e2-249">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="c43e2-249">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="c43e2-250">Get-Process</span><span class="sxs-lookup"><span data-stu-id="c43e2-250">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="c43e2-251">Start-Service</span><span class="sxs-lookup"><span data-stu-id="c43e2-251">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="c43e2-252">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="c43e2-252">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="c43e2-253">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="c43e2-253">Wait-Process</span></span>](Wait-Process.md)
