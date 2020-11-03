---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: b6147b35a8818cf448b1e23f5458550d1c6e5c50
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "93230193"
---
# <span data-ttu-id="2f1e1-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="2f1e1-103">Start-Process</span></span>

## <span data-ttu-id="2f1e1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2f1e1-104">SYNOPSIS</span></span>
<span data-ttu-id="2f1e1-105">Запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="2f1e1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f1e1-106">SYNTAX</span></span>

### <span data-ttu-id="2f1e1-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2f1e1-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [<CommonParameters>]
```

### <span data-ttu-id="2f1e1-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="2f1e1-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [<CommonParameters>]
```

## <span data-ttu-id="2f1e1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f1e1-109">DESCRIPTION</span></span>

<span data-ttu-id="2f1e1-110">`Start-Process`Командлет запускает один или несколько процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="2f1e1-111">По умолчанию `Start-Process` создает новый процесс, который наследует все переменные среды, определенные в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="2f1e1-112">Чтобы указать программу, выполняемую в процессе, введите исполняемый файл или файл скрипта, либо файл, который может быть открыт с помощью имеющейся на компьютере программы.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="2f1e1-113">Если указан неисполняемый файл, `Start-Process` программа запускает программу, связанную с файлом, аналогично `Invoke-Item` командлету.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="2f1e1-114">Параметры можно использовать `Start-Process` для указания параметров, таких как загрузка профиля пользователя, запуск процесса в новом окне или использование альтернативных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="2f1e1-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="2f1e1-115">EXAMPLES</span></span>

### <span data-ttu-id="2f1e1-116">Пример 1. Запуск процесса, использующего значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2f1e1-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="2f1e1-117">В этом примере запускается процесс, который использует `Sort.exe` файл в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="2f1e1-118">Команда использует все значения по умолчанию, включая стиль окна по умолчанию, рабочую папку и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="2f1e1-119">Пример 2. Печать текстового файла</span><span class="sxs-lookup"><span data-stu-id="2f1e1-119">Example 2: Print a text file</span></span>

<span data-ttu-id="2f1e1-120">В этом примере запускается процесс, который выводит `C:\PS-Test\MyFile.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="2f1e1-121">Пример 3. Запуск процесса для сортировки элементов в новый файл</span><span class="sxs-lookup"><span data-stu-id="2f1e1-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="2f1e1-122">В этом примере запускается процесс, который сортирует элементы в `Testsort.txt` файле и возвращает отсортированные элементы в `Sorted.txt` файлах.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="2f1e1-123">Все ошибки записываются в `SortError.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="2f1e1-124">Параметр **усеневенвиронмент** указывает, что процесс выполняется с собственными переменными среды.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="2f1e1-125">Пример 4. Запуск процесса в развернутом окне</span><span class="sxs-lookup"><span data-stu-id="2f1e1-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="2f1e1-126">В этом примере запускается `Notepad.exe` процесс.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="2f1e1-127">Окно разворачивается во весь экран и удерживается до завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="2f1e1-128">Пример 5. Запуск PowerShell от имени администратора</span><span class="sxs-lookup"><span data-stu-id="2f1e1-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="2f1e1-129">В этом примере запускается PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="2f1e1-130">Пример 6. Использование различных команд для запуска процесса</span><span class="sxs-lookup"><span data-stu-id="2f1e1-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="2f1e1-131">В этом примере показано, как найти команды, которые можно использовать при запуске процесса.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="2f1e1-132">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="2f1e1-133">В примере используется `New-Object` для создания объекта **System. Diagnostics. ProcessStartInfo** для **PowerShell.exe** — файла, который выполняется в процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="2f1e1-134">Свойство **Verbs** объекта **ProcessStartInfo** показывает, что можно использовать команды **Open** и **runas** с `PowerShell.exe` или с любым процессом, запускающим `.exe` файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="2f1e1-135">Пример 7. Указание аргументов для процесса</span><span class="sxs-lookup"><span data-stu-id="2f1e1-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="2f1e1-136">Обе команды запускают интерпретатор команд Windows, выполняя `dir` команду в `Program Files` папке.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="2f1e1-137">Поскольку это переключка содержит пробел, значение должно заключаться в экранированные кавычки.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="2f1e1-138">Обратите внимание, что первая команда указывает строку как **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-138">Note that the first command specifies a string as **ArgumentList** .</span></span> <span data-ttu-id="2f1e1-139">Вторая команда является массивом строк.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="2f1e1-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2f1e1-140">PARAMETERS</span></span>

### <span data-ttu-id="2f1e1-141">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="2f1e1-141">-ArgumentList</span></span>

<span data-ttu-id="2f1e1-142">Указывает параметры или значения параметров, которые следует использовать при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="2f1e1-143">Аргументы можно принимать как одну строку с аргументами, разделенными пробелами, или как массив строк, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="2f1e1-144">Если параметры или значения параметров содержат пробел, их необходимо заключить в escape-символы, заключенные в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="2f1e1-145">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="2f1e1-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="2f1e1-146">-Credential</span></span>

<span data-ttu-id="2f1e1-147">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2f1e1-148">По умолчанию командлет использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="2f1e1-149">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-149">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2f1e1-150">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="2f1e1-151">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2f1e1-152">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="2f1e1-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2f1e1-153">-FilePath</span></span>

<span data-ttu-id="2f1e1-154">Указывает необязательный путь и имя файла программы, выполняемой в процессе.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="2f1e1-155">Введите имя исполняемого файла или документа, например `.txt` `.doc` файла или, связанного с программой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="2f1e1-156">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-156">This parameter is required.</span></span>

<span data-ttu-id="2f1e1-157">Если указано только имя файла, используйте параметр **WorkingDirectory** , чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f1e1-158">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="2f1e1-158">-LoadUserProfile</span></span>

<span data-ttu-id="2f1e1-159">Указывает, что этот командлет загружает профиль пользователя Windows, хранящийся в разделе `HKEY_USERS` реестра для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span>

<span data-ttu-id="2f1e1-160">Этот параметр не влияет на профили PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-160">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="2f1e1-161">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-161">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

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

### <span data-ttu-id="2f1e1-162">-NoNewWindow</span><span class="sxs-lookup"><span data-stu-id="2f1e1-162">-NoNewWindow</span></span>

<span data-ttu-id="2f1e1-163">Предотвращает запуск процесса в новом окне.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-163">Start the new process in the current console window.</span></span> <span data-ttu-id="2f1e1-164">По умолчанию PowerShell открывает новое окно.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-164">By default PowerShell opens a new window.</span></span>

<span data-ttu-id="2f1e1-165">Использовать параметры **NoNewWindow** и **WindowStyle** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-165">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

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

### <span data-ttu-id="2f1e1-166">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2f1e1-166">-PassThru</span></span>

<span data-ttu-id="2f1e1-167">Возвращает объект процесса для каждого запущенного командлетом процесса</span><span class="sxs-lookup"><span data-stu-id="2f1e1-167">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="2f1e1-168">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-168">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2f1e1-169">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="2f1e1-169">-RedirectStandardError</span></span>

<span data-ttu-id="2f1e1-170">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-170">Specifies a file.</span></span> <span data-ttu-id="2f1e1-171">Этот командлет отправляет все ошибки, созданные процессом, в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-171">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="2f1e1-172">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-172">Enter the path and filename.</span></span> <span data-ttu-id="2f1e1-173">По умолчанию все ошибки отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-173">By default, the errors are displayed in the console.</span></span>

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

### <span data-ttu-id="2f1e1-174">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="2f1e1-174">-RedirectStandardInput</span></span>

<span data-ttu-id="2f1e1-175">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-175">Specifies a file.</span></span> <span data-ttu-id="2f1e1-176">Этот командлет считывает входные данные из указанного файла.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-176">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="2f1e1-177">Введите путь и имя входного файла.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-177">Enter the path and filename of the input file.</span></span> <span data-ttu-id="2f1e1-178">По умолчанию процесс получает входные данные с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-178">By default, the process gets its input from the keyboard.</span></span>

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

### <span data-ttu-id="2f1e1-179">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="2f1e1-179">-RedirectStandardOutput</span></span>

<span data-ttu-id="2f1e1-180">Указывает файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-180">Specifies a file.</span></span> <span data-ttu-id="2f1e1-181">Этот командлет отправляет выходные данные, созданные процессом, в указанный вами файл.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-181">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="2f1e1-182">Введите путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-182">Enter the path and filename.</span></span> <span data-ttu-id="2f1e1-183">По умолчанию выходные данные отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-183">By default, the output is displayed in the console.</span></span>

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

### <span data-ttu-id="2f1e1-184">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="2f1e1-184">-UseNewEnvironment</span></span>

<span data-ttu-id="2f1e1-185">Указывает, что этот командлет использует новые переменные среды, заданные для процесса.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-185">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="2f1e1-186">По умолчанию запущенный процесс выполняется с переменными среды, унаследованными от родительского процесса.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-186">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

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

### <span data-ttu-id="2f1e1-187">-Verb</span><span class="sxs-lookup"><span data-stu-id="2f1e1-187">-Verb</span></span>

<span data-ttu-id="2f1e1-188">Задает команду, используемую при запуске этого командлета.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-188">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="2f1e1-189">Доступные команды определяются расширением имени файла, который выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-189">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="2f1e1-190">В приведенной ниже таблице показаны команды, доступные для некоторых распространенных типов файлов.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-190">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="2f1e1-191">Тип файла</span><span class="sxs-lookup"><span data-stu-id="2f1e1-191">File type</span></span> |                <span data-ttu-id="2f1e1-192">Команды</span><span class="sxs-lookup"><span data-stu-id="2f1e1-192">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="2f1e1-193">.cmd</span><span class="sxs-lookup"><span data-stu-id="2f1e1-193">.cmd</span></span>      | <span data-ttu-id="2f1e1-194">Правка, открытие, печать, Запуск от имени, выполняющийся</span><span class="sxs-lookup"><span data-stu-id="2f1e1-194">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="2f1e1-195">EXE</span><span class="sxs-lookup"><span data-stu-id="2f1e1-195">.exe</span></span>      | <span data-ttu-id="2f1e1-196">Open, RunAs, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="2f1e1-196">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="2f1e1-197">.txt</span><span class="sxs-lookup"><span data-stu-id="2f1e1-197">.txt</span></span>      | <span data-ttu-id="2f1e1-198">Открытие, печать, Принтто</span><span class="sxs-lookup"><span data-stu-id="2f1e1-198">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="2f1e1-199">.wav</span><span class="sxs-lookup"><span data-stu-id="2f1e1-199">.wav</span></span>      | <span data-ttu-id="2f1e1-200">Открыть, воспроизвести</span><span class="sxs-lookup"><span data-stu-id="2f1e1-200">Open, Play</span></span>                          |

<span data-ttu-id="2f1e1-201">Чтобы найти команды, которые можно использовать с файлом, выполняемым в процессе, используйте `New-Object` командлет, чтобы создать объект **System. Diagnostics. ProcessStartInfo** для файла.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-201">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="2f1e1-202">Доступные команды находятся в свойстве **Verbs** объекта **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-202">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="2f1e1-203">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-203">For details, see the examples.</span></span>

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

### <span data-ttu-id="2f1e1-204">-Wait</span><span class="sxs-lookup"><span data-stu-id="2f1e1-204">-Wait</span></span>

<span data-ttu-id="2f1e1-205">Указывает, что этот командлет ожидает завершения указанного процесса и его потомков, прежде чем принимать дополнительные входные данные.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-205">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="2f1e1-206">Этот параметр подавляет командную строку или оставляет окно до завершения процессов.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-206">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="2f1e1-207">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="2f1e1-207">-WindowStyle</span></span>

<span data-ttu-id="2f1e1-208">Определяет состояние окна для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-208">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="2f1e1-209">Допустимые значения для этого параметра: **нормальный** , **скрытый** , **сведенный** и **развернутый** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-209">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized** .</span></span> <span data-ttu-id="2f1e1-210">Значение по умолчанию — **Обычная** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-210">The default value is **Normal** .</span></span>

<span data-ttu-id="2f1e1-211">Использовать параметры **WindowStyle** и **NoNewWindow** в одной и той же команде нельзя.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-211">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

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

### <span data-ttu-id="2f1e1-212">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="2f1e1-212">-WorkingDirectory</span></span>

<span data-ttu-id="2f1e1-213">Указывает расположение, в котором должен начинаться новый процесс.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-213">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="2f1e1-214">По умолчанию это расположение исполняемого файла или документа, который запускается.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-214">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="2f1e1-215">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-215">Wildcards are not supported.</span></span> <span data-ttu-id="2f1e1-216">Имя пути не должно содержать символы, интерпретируемые как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-216">The path name must not contain characters that would be interpreted as wildcards.</span></span>

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

### <span data-ttu-id="2f1e1-217">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2f1e1-217">CommonParameters</span></span>

<span data-ttu-id="2f1e1-218">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f1e1-219">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f1e1-220">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2f1e1-220">INPUTS</span></span>

### <span data-ttu-id="2f1e1-221">Нет</span><span class="sxs-lookup"><span data-stu-id="2f1e1-221">None</span></span>

<span data-ttu-id="2f1e1-222">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-222">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2f1e1-223">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2f1e1-223">OUTPUTS</span></span>

### <span data-ttu-id="2f1e1-224">Нет, System. Диагностика. Process</span><span class="sxs-lookup"><span data-stu-id="2f1e1-224">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="2f1e1-225">Этот командлет создает объект **System. Diagnostics. Process** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-225">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="2f1e1-226">В противном случае командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-226">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="2f1e1-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2f1e1-227">NOTES</span></span>

- <span data-ttu-id="2f1e1-228">Этот командлет реализуется с помощью метода **Start** класса **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-228">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="2f1e1-229">Дополнительные сведения об этом методе см. в разделе [метод Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-229">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="2f1e1-230">В Windows при использовании **усеневенвиронмент** новый процесс запускается только с переменными среды по умолчанию, определенными для области **компьютера** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-230">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="2f1e1-231">Это влияет на то, что параметр `$env:USERNAME` имеет значение **System** .</span><span class="sxs-lookup"><span data-stu-id="2f1e1-231">This has the side affect that the `$env:USERNAME` is set to **SYSTEM** .</span></span> <span data-ttu-id="2f1e1-232">Ни одна из переменных из **пользовательской** области не включена.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-232">None of the variables from the **User** scope are included.</span></span>

## <span data-ttu-id="2f1e1-233">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2f1e1-233">RELATED LINKS</span></span>

[<span data-ttu-id="2f1e1-234">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="2f1e1-234">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="2f1e1-235">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="2f1e1-235">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="2f1e1-236">Get-Process</span><span class="sxs-lookup"><span data-stu-id="2f1e1-236">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="2f1e1-237">Start-Service</span><span class="sxs-lookup"><span data-stu-id="2f1e1-237">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="2f1e1-238">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="2f1e1-238">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="2f1e1-239">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="2f1e1-239">Wait-Process</span></span>](Wait-Process.md)
