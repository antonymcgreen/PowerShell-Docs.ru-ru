---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: 543c2b683ca3631e2e05f57d9c70ff4455071e4b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229430"
---
# <span data-ttu-id="4f359-103">Get-Process</span><span class="sxs-lookup"><span data-stu-id="4f359-103">Get-Process</span></span>

## <span data-ttu-id="4f359-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4f359-104">SYNOPSIS</span></span>
<span data-ttu-id="4f359-105">Возвращает процессы, запущенные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f359-105">Gets the processes that are running on the local computer.</span></span>

## <span data-ttu-id="4f359-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f359-106">SYNTAX</span></span>

### <span data-ttu-id="4f359-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4f359-107">Name (Default)</span></span>

```
Get-Process [[-Name] <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="4f359-108">намевисусернаме</span><span class="sxs-lookup"><span data-stu-id="4f359-108">NameWithUserName</span></span>

```
Get-Process [[-Name] <String[]>] -IncludeUserName [<CommonParameters>]
```

### <span data-ttu-id="4f359-109">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4f359-109">Id</span></span>

```
Get-Process -Id <Int32[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="4f359-110">идвисусернаме</span><span class="sxs-lookup"><span data-stu-id="4f359-110">IdWithUserName</span></span>

```
Get-Process -Id <Int32[]> -IncludeUserName [<CommonParameters>]
```

### <span data-ttu-id="4f359-111">InputObject</span><span class="sxs-lookup"><span data-stu-id="4f359-111">InputObject</span></span>

```
Get-Process -InputObject <Process[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="4f359-112">инпутобжектвисусернаме</span><span class="sxs-lookup"><span data-stu-id="4f359-112">InputObjectWithUserName</span></span>

```
Get-Process -InputObject <Process[]> -IncludeUserName [<CommonParameters>]
```

## <span data-ttu-id="4f359-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4f359-113">DESCRIPTION</span></span>

<span data-ttu-id="4f359-114">`Get-Process`Командлет возвращает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f359-114">The `Get-Process` cmdlet gets the processes on a local computer.</span></span>

<span data-ttu-id="4f359-115">Без параметров этот командлет получает все процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f359-115">Without parameters, this cmdlet gets all of the processes on the local computer.</span></span>
<span data-ttu-id="4f359-116">Можно также указать конкретный процесс по имени или ИДЕНТИФИКАТОРу процесса (PID) или передать объект процесса через конвейер в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="4f359-116">You can also specify a particular process by process name or process ID (PID) or pass a process object through the pipeline to this cmdlet.</span></span>

<span data-ttu-id="4f359-117">По умолчанию этот командлет возвращает объект Process с подробными сведениями о процессе и поддерживает методы, позволяющие запускать и прекращать процесс.</span><span class="sxs-lookup"><span data-stu-id="4f359-117">By default, this cmdlet returns a process object that has detailed information about the process and supports methods that let you start and stop the process.</span></span>
<span data-ttu-id="4f359-118">Можно также использовать параметры `Get-Process` командлета, чтобы получить сведения о версии файла для программы, выполняемой в процессе, и получить модули, загруженные процессом.</span><span class="sxs-lookup"><span data-stu-id="4f359-118">You can also use the parameters of the `Get-Process` cmdlet to get file version information for the program that runs in the process and to get the modules that the process loaded.</span></span>

## <span data-ttu-id="4f359-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="4f359-119">EXAMPLES</span></span>

### <span data-ttu-id="4f359-120">Пример 1. Получение списка всех активных процессов на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="4f359-120">Example 1: Get a list of all active processes on the local computer</span></span>

```powershell
Get-Process
```

<span data-ttu-id="4f359-121">Эта команда возвращает список всех активных процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f359-121">This command gets a list of all active processes running on the local computer.</span></span>
<span data-ttu-id="4f359-122">Определение каждого столбца см. в разделе [Примечания](#notes) .</span><span class="sxs-lookup"><span data-stu-id="4f359-122">For a definition of each column, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="4f359-123">Пример 2. получение всех доступных данных о одном или нескольких процессах</span><span class="sxs-lookup"><span data-stu-id="4f359-123">Example 2: Get all available data about one or more processes</span></span>

```powershell
Get-Process winword, explorer | Format-List *
```

<span data-ttu-id="4f359-124">Эта команда возвращает все доступные данные о процессах Winword и проводника на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4f359-124">This command gets all available data about the Winword and Explorer processes on the computer.</span></span>
<span data-ttu-id="4f359-125">В нем используется параметр **Name** для указания процессов, но в нем опущено необязательное имя параметра.</span><span class="sxs-lookup"><span data-stu-id="4f359-125">It uses the **Name** parameter to specify the processes, but it omits the optional parameter name.</span></span>
<span data-ttu-id="4f359-126">Оператор конвейера `|` передает данные в `Format-List` командлет, который отображает все доступные свойства `*` объектов Process Winword и проводника.</span><span class="sxs-lookup"><span data-stu-id="4f359-126">The pipeline operator `|` passes the data to the `Format-List` cmdlet, which displays all available properties `*` of the Winword and Explorer process objects.</span></span>

<span data-ttu-id="4f359-127">Процессы также можно определить по идентификаторам (PID).</span><span class="sxs-lookup"><span data-stu-id="4f359-127">You can also identify the processes by their process IDs.</span></span>
<span data-ttu-id="4f359-128">Например, `Get-Process -Id 664, 2060` .</span><span class="sxs-lookup"><span data-stu-id="4f359-128">For instance, `Get-Process -Id 664, 2060`.</span></span>

### <span data-ttu-id="4f359-129">Пример 3. получение всех процессов с рабочим набором, превышающим указанный размер</span><span class="sxs-lookup"><span data-stu-id="4f359-129">Example 3: Get all processes with a working set greater than a specified size</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

<span data-ttu-id="4f359-130">Эта команда возвращает все процессы, размер рабочего набора которых превышает 20 МБ.</span><span class="sxs-lookup"><span data-stu-id="4f359-130">This command gets all processes that have a working set greater than 20 MB.</span></span>
<span data-ttu-id="4f359-131">Он использует `Get-Process`  командлет для получения всех запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="4f359-131">It uses the `Get-Process`  cmdlet to get all running processes.</span></span>
<span data-ttu-id="4f359-132">Оператор конвейера `|` передает объекты процесса в `Where-Object` командлет, который выбирает только объект со значением, превышающим 20 000 000 байт для свойства " **рабочее** множество".</span><span class="sxs-lookup"><span data-stu-id="4f359-132">The pipeline operator `|` passes the process objects to the `Where-Object` cmdlet, which selects only the object with a value greater than 20,000,000 bytes for the **WorkingSet** property.</span></span>

<span data-ttu-id="4f359-133">**Рабочее** множество — это одно из многих свойств объектов Process.</span><span class="sxs-lookup"><span data-stu-id="4f359-133">**WorkingSet** is one of many properties of process objects.</span></span>
<span data-ttu-id="4f359-134">Чтобы просмотреть все свойства, введите `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="4f359-134">To see all of the properties, type `Get-Process | Get-Member`.</span></span>
<span data-ttu-id="4f359-135">По умолчанию значения всех свойств объема указываются в байтах, несмотря на то что по умолчанию отображаются они отображаются в килобайтах и мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="4f359-135">By default, the values of all amount properties are in bytes, even though the default display lists them in kilobytes and megabytes.</span></span>

### <span data-ttu-id="4f359-136">Пример 4. Вывод списка процессов на компьютере в группах на основе приоритета</span><span class="sxs-lookup"><span data-stu-id="4f359-136">Example 4: List processes on the computer in groups based on priority</span></span>

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

<span data-ttu-id="4f359-137">Эти команды выводит список процессов на компьютере в группах в зависимости от их класса приоритета.</span><span class="sxs-lookup"><span data-stu-id="4f359-137">These commands list the processes on the computer in groups based on their priority class.</span></span>
<span data-ttu-id="4f359-138">Первая команда получает все процессы на компьютере, а затем сохраняет их в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="4f359-138">The first command gets all the processes on the computer and then stores them in the `$A` variable.</span></span>

<span data-ttu-id="4f359-139">Вторая команда передает объект **процесса** , хранящийся в `$A` переменной `Get-Process` , в командлет, а затем — в `Format-Table` командлет, который форматирует процессы с помощью представления **Priority** .</span><span class="sxs-lookup"><span data-stu-id="4f359-139">The second command pipes the **Process** object stored in the `$A` variable to the `Get-Process` cmdlet, then to the `Format-Table` cmdlet, which formats the processes by using the **Priority** view.</span></span>

<span data-ttu-id="4f359-140">Представление **приоритетов** и другие представления определяются в файлах форматирования ps1xml в домашнем каталоге PowerShell ( `$pshome` ).</span><span class="sxs-lookup"><span data-stu-id="4f359-140">The **Priority** view, and other views, are defined in the PS1XML format files in the PowerShell home directory (`$pshome`).</span></span>

### <span data-ttu-id="4f359-141">Пример 5. Добавление свойства к отображению стандартного Get-Process вывода</span><span class="sxs-lookup"><span data-stu-id="4f359-141">Example 5: Add a property to the standard Get-Process output display</span></span>

```powershell
Get-Process pwsh | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 .           pwsh
     6 23500 31348   142 2.75   4016 .           pwsh
    27 54572 54520   576 5.52   4428 .           pwsh
```

<span data-ttu-id="4f359-142">Этот пример предоставляет `Format-Table` команду, которая добавляет свойство **MachineName** к стандартному `Get-Process` отображению выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4f359-142">This example provides a `Format-Table` command that adds the **MachineName** property to the standard `Get-Process` output display.</span></span>

### <span data-ttu-id="4f359-143">Пример 6. Получение сведений о версии для процесса</span><span class="sxs-lookup"><span data-stu-id="4f359-143">Example 6: Get version information for a process</span></span>

```powershell
Get-Process pwsh -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.2            6.1.2            C:\Program Files\PowerShell\6\pwsh.exe
```

<span data-ttu-id="4f359-144">Эта команда использует параметр **FileVersionInfo** для получения сведений о версии файла pwsh.exe, который является основным модулем для процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f359-144">This command uses the **FileVersionInfo** parameter to get the version information for the pwsh.exe file that is the main module for the PowerShell process.</span></span>

<span data-ttu-id="4f359-145">Чтобы выполнить эту команду с процессами, которые не являются владельцами в Windows Vista и более поздних версиях Windows, необходимо открыть PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="4f359-145">To run this command with processes that you do not own on Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="4f359-146">Пример 7. Загрузка модулей, загруженных с указанным процессом</span><span class="sxs-lookup"><span data-stu-id="4f359-146">Example 7: Get modules loaded with the specified process</span></span>

```powershell
Get-Process SQL* -Module
```

<span data-ttu-id="4f359-147">Эта команда использует параметр **module** для получения модулей, загруженных процессом.</span><span class="sxs-lookup"><span data-stu-id="4f359-147">This command uses the **Module** parameter to get the modules that have been loaded by the process.</span></span>
<span data-ttu-id="4f359-148">Эта команда возвращает модули для процессов, имена которых начинаются с SQL.</span><span class="sxs-lookup"><span data-stu-id="4f359-148">This command gets the modules for the processes that have names that begin with SQL.</span></span>

<span data-ttu-id="4f359-149">Чтобы выполнить эту команду в Windows Vista и более поздних версиях Windows с несобственными процессами, необходимо запустить PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="4f359-149">To run this command on Windows Vista and later versions of Windows with processes that you do not own, you must start PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="4f359-150">Пример 8. Поиск владельца процесса</span><span class="sxs-lookup"><span data-stu-id="4f359-150">Example 8: Find the owner of a process</span></span>

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     pwsh
```

<span data-ttu-id="4f359-151">В этом примере показано, как найти владельца процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-151">This command shows how to find the owner of a process.</span></span>
<span data-ttu-id="4f359-152">В Windows параметр **IncludeUserName** требует повышенных прав пользователя (Запуск от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="4f359-152">On Windows, the **IncludeUserName** parameter requires elevated user rights (Run as Administrator).</span></span>
<span data-ttu-id="4f359-153">Результат показывает, что владелец — Domain01\user01.</span><span class="sxs-lookup"><span data-stu-id="4f359-153">The output reveals that the owner is Domain01\user01.</span></span>

### <span data-ttu-id="4f359-154">Пример 9. Использование автоматической переменной для обнаружения процесса, в котором размещен текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="4f359-154">Example 9: Use an automatic variable to identify the process hosting the current session</span></span>

```powershell
Get-Process pwsh
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21     105.95       4.33    1192  10 pwsh
    79    83.81     117.61       2.16   10580  10 pwsh
```

```powershell
Get-Process -Id $PID
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21      77.53       4.39    1192  10 pwsh
```

<span data-ttu-id="4f359-155">Эти команды показывают, как использовать `$PID` автоматическую переменную для указания процесса, в котором размещается текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f359-155">These commands show how to use the `$PID` automatic variable to identify the process that is hosting the current PowerShell session.</span></span>
<span data-ttu-id="4f359-156">Этот метод можно использовать, чтобы отличить ведущий процесс от других процессов PowerShell, которые может потребоваться приостанавливаться или закрыть.</span><span class="sxs-lookup"><span data-stu-id="4f359-156">You can use this method to distinguish the host process from other PowerShell processes that you might want to stop or close.</span></span>

<span data-ttu-id="4f359-157">Первая команда получает все процессы PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f359-157">The first command gets all of the PowerShell processes in the current session.</span></span>

<span data-ttu-id="4f359-158">Вторая команда получает процесс PowerShell, в котором размещается текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="4f359-158">The second command gets the PowerShell process that is hosting the current session.</span></span>

### <span data-ttu-id="4f359-159">Пример 10. получение всех процессов, имеющих заголовок главного окна, и их отображение в таблице</span><span class="sxs-lookup"><span data-stu-id="4f359-159">Example 10: Get all processes that have a main window title and display them in a table</span></span>

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

<span data-ttu-id="4f359-160">Эта команда возвращает все процессы с заголовком главного окна и отображает их в таблице, где также указаны идентификатор и имя процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-160">This command gets all the processes that have a main window title, and it displays them in a table with the process ID and the process name.</span></span>

<span data-ttu-id="4f359-161">Свойство **маинвиндовтитле** — это лишь одно из многих полезных свойств объекта **Process** , который `Get-Process` возвращает.</span><span class="sxs-lookup"><span data-stu-id="4f359-161">The **mainWindowTitle** property is just one of many useful properties of the **Process** object that `Get-Process` returns.</span></span>
<span data-ttu-id="4f359-162">Чтобы просмотреть все свойства, передайте результаты выполнения `Get-Process` команды в `Get-Member` командлет `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="4f359-162">To view all of the properties, pipe the results of a `Get-Process` command to the `Get-Member` cmdlet `Get-Process | Get-Member`.</span></span>

## <span data-ttu-id="4f359-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f359-163">PARAMETERS</span></span>

### <span data-ttu-id="4f359-164">-FileVersionInfo</span><span class="sxs-lookup"><span data-stu-id="4f359-164">-FileVersionInfo</span></span>

<span data-ttu-id="4f359-165">Указывает, что этот командлет получает сведения о версии файла для программы, которая выполняется в процессе.</span><span class="sxs-lookup"><span data-stu-id="4f359-165">Indicates that this cmdlet gets the file version information for the program that runs in the process.</span></span>

<span data-ttu-id="4f359-166">В Windows Vista и более поздних версиях Windows необходимо открыть PowerShell с параметром Запуск от имени администратора, чтобы использовать этот параметр для процессов, которыми вы не владеете.</span><span class="sxs-lookup"><span data-stu-id="4f359-166">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="4f359-167">Чтобы получить сведения о версии файла для процесса на удаленном компьютере, используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="4f359-167">To get file version information for a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="4f359-168">Использование этого параметра эквивалентно получению свойства **маинмодуле. FileVersionInfo** каждого объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-168">Using this parameter is equivalent to getting the **MainModule.FileVersionInfo** property of each process object.</span></span>
<span data-ttu-id="4f359-169">При использовании этого параметра `Get-Process` возвращает объект **FileVersionInfo** **System. Diagnostics. FileVersionInfo** , а не объект процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-169">When you use this parameter, `Get-Process` returns a **FileVersionInfo** object **System.Diagnostics.FileVersionInfo** , not a process object.</span></span>
<span data-ttu-id="4f359-170">Таким образом, нельзя передать выходные данные команды в командлет, который предполагает объект процесса, например `Stop-Process` .</span><span class="sxs-lookup"><span data-stu-id="4f359-170">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f359-171">-Id</span><span class="sxs-lookup"><span data-stu-id="4f359-171">-Id</span></span>

<span data-ttu-id="4f359-172">Указывает один или несколько процессов по идентификатору процесса (PID).</span><span class="sxs-lookup"><span data-stu-id="4f359-172">Specifies one or more processes by process ID (PID).</span></span>
<span data-ttu-id="4f359-173">При указании нескольких идентификаторов разделяйте их запятыми.</span><span class="sxs-lookup"><span data-stu-id="4f359-173">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="4f359-174">Чтобы найти идентификатор процесса, введите `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="4f359-174">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id, IdWithUserName
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4f359-175">-IncludeUserName</span><span class="sxs-lookup"><span data-stu-id="4f359-175">-IncludeUserName</span></span>

<span data-ttu-id="4f359-176">Указывает, что значение UserName объекта **процесса** возвращается с результатами выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="4f359-176">Indicates that the UserName value of the **Process** object is returned with results of the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f359-177">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4f359-177">-InputObject</span></span>

<span data-ttu-id="4f359-178">Указывает один или несколько объектов процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-178">Specifies one or more process objects.</span></span>
<span data-ttu-id="4f359-179">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="4f359-179">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4f359-180">-Module</span><span class="sxs-lookup"><span data-stu-id="4f359-180">-Module</span></span>

<span data-ttu-id="4f359-181">Указывает, что этот командлет получает модули, загруженные процессами.</span><span class="sxs-lookup"><span data-stu-id="4f359-181">Indicates that this cmdlet gets the modules that have been loaded by the processes.</span></span>

<span data-ttu-id="4f359-182">В Windows Vista и более поздних версиях Windows необходимо открыть PowerShell с параметром Запуск от имени администратора, чтобы использовать этот параметр для процессов, которыми вы не владеете.</span><span class="sxs-lookup"><span data-stu-id="4f359-182">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="4f359-183">Чтобы получить модули, загруженные процессом на удаленном компьютере, используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="4f359-183">To get the modules that have been loaded by a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="4f359-184">Этот параметр эквивалентен получению свойства **modules** каждого объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-184">This parameter is equivalent to getting the **Modules** property of each process object.</span></span>
<span data-ttu-id="4f359-185">При использовании этого параметра командлет возвращает объект **ProcessModule** **. Diagnostics. ProcessModule** , а не объект процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-185">When you use this parameter, this cmdlet returns a **ProcessModule** object **System.Diagnostics.ProcessModule** , not a process object.</span></span>
<span data-ttu-id="4f359-186">Таким образом, нельзя передать выходные данные команды в командлет, который предполагает объект процесса, например `Stop-Process` .</span><span class="sxs-lookup"><span data-stu-id="4f359-186">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

<span data-ttu-id="4f359-187">При одновременном использовании параметров *module* и **FileVersionInfo** в одной команде этот командлет возвращает объект **FileVersionInfo** со сведениями о версии файла всех модулей.</span><span class="sxs-lookup"><span data-stu-id="4f359-187">When you use both the *Module* and **FileVersionInfo** parameters in the same command, this cmdlet returns a **FileVersionInfo** object with information about the file version of all modules.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f359-188">-Name</span><span class="sxs-lookup"><span data-stu-id="4f359-188">-Name</span></span>

<span data-ttu-id="4f359-189">Указывает один или несколько процессов по имени процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-189">Specifies one or more processes by process name.</span></span>
<span data-ttu-id="4f359-190">Можно ввести несколько имен процессов (разделенных запятыми) и использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4f359-190">You can type multiple process names (separated by commas) and use wildcard characters.</span></span>
<span data-ttu-id="4f359-191">Имя параметра (Name) указывать необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f359-191">The parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="4f359-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4f359-192">CommonParameters</span></span>

<span data-ttu-id="4f359-193">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4f359-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f359-194">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4f359-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4f359-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4f359-195">INPUTS</span></span>

### <span data-ttu-id="4f359-196">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="4f359-196">System.Diagnostics.Process</span></span>

<span data-ttu-id="4f359-197">Объект процесса можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4f359-197">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="4f359-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4f359-198">OUTPUTS</span></span>

### <span data-ttu-id="4f359-199">System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule</span><span class="sxs-lookup"><span data-stu-id="4f359-199">System.Diagnostics.Process, System.Diagnostics.FileVersionInfo, System.Diagnostics.ProcessModule</span></span>

<span data-ttu-id="4f359-200">По умолчанию этот командлет возвращает объект **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="4f359-200">By default, this cmdlet returns a **System.Diagnostics.Process** object.</span></span>
<span data-ttu-id="4f359-201">При использовании параметра **FileVersionInfo** возвращается объект **System. Diagnostics. FileVersionInfo** .</span><span class="sxs-lookup"><span data-stu-id="4f359-201">If you use the **FileVersionInfo** parameter, it returns a **System.Diagnostics.FileVersionInfo** object.</span></span>
<span data-ttu-id="4f359-202">Если вы используете параметр **module** без параметра **FileVersionInfo** , он возвращает объект **System. Diagnostics. ProcessModule** .</span><span class="sxs-lookup"><span data-stu-id="4f359-202">If you use the **Module** parameter, without the **FileVersionInfo** parameter, it returns a **System.Diagnostics.ProcessModule** object.</span></span>

## <span data-ttu-id="4f359-203">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4f359-203">NOTES</span></span>

- <span data-ttu-id="4f359-204">Вы также можете ссылаться на этот командлет по его встроенным псевдонимам, PS и GPS.</span><span class="sxs-lookup"><span data-stu-id="4f359-204">You can also refer to this cmdlet by its built-in aliases, ps and gps.</span></span> <span data-ttu-id="4f359-205">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="4f359-205">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="4f359-206">На компьютерах, работающих под управлением 64-разрядной версии Windows, 64-разрядная версия PowerShell получает только 64-разрядные модули процесса, а в 32-разрядной версии PowerShell — только модули с 32-битным процессом.</span><span class="sxs-lookup"><span data-stu-id="4f359-206">On computers that are running a 64-bit version of Windows, the 64-bit version of PowerShell gets only 64-bit process modules and the 32-bit version of PowerShell gets only 32-bit process modules.</span></span>
- <span data-ttu-id="4f359-207">Вы можете использовать свойства и методы Win32_Process объекта инструментарий управления Windows (WMI) (WMI) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f359-207">You can use the properties and methods of the Windows Management Instrumentation (WMI) Win32_Process object in PowerShell.</span></span> <span data-ttu-id="4f359-208">Дополнительные сведения см `Get-WmiObject` . в разделе и пакете SDK для инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="4f359-208">For information, see `Get-WmiObject` and the WMI SDK.</span></span>
- <span data-ttu-id="4f359-209">По умолчанию процесс отображается как таблица, которая содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="4f359-209">The default display of a process is a table that includes the following columns.</span></span> <span data-ttu-id="4f359-210">Описание всех свойств объектов Process см. в разделе [Свойства процесса](/dotnet/api/system.diagnostics.process) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="4f359-210">For a description of all of the properties of process objects, see [Process Properties](/dotnet/api/system.diagnostics.process) in the MSDN library.</span></span>
  - <span data-ttu-id="4f359-211">Handles: количество дескрипторов, открытых процессом.</span><span class="sxs-lookup"><span data-stu-id="4f359-211">Handles: The number of handles that the process has opened.</span></span>
  - <span data-ttu-id="4f359-212">NPM (K): объем нестраничной памяти, используемой процессом, в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="4f359-212">NPM(K): The amount of non-paged memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="4f359-213">PM (K): объем выгружаемой памяти, используемой процессом, в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="4f359-213">PM(K): The amount of pageable memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="4f359-214">WS (K): размер рабочего набора процесса в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="4f359-214">WS(K): The size of the working set of the process, in kilobytes.</span></span>
    <span data-ttu-id="4f359-215">Рабочий набор состоит из страниц памяти, на которые недавно ссылался процесс.</span><span class="sxs-lookup"><span data-stu-id="4f359-215">The working set consists of the pages of memory that were recently referenced by the process.</span></span>
  - <span data-ttu-id="4f359-216">VM (M): объем виртуальной памяти, используемой процессом, в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="4f359-216">VM(M): The amount of virtual memory that the process is using, in megabytes.</span></span>
    <span data-ttu-id="4f359-217">Виртуальная память используется для хранения файлов подкачки на диске.</span><span class="sxs-lookup"><span data-stu-id="4f359-217">Virtual memory includes storage in the paging files on disk.</span></span>
  - <span data-ttu-id="4f359-218">ЦП: количество процессорного времени, которое процесс использовал во всех процессорах (в секундах).</span><span class="sxs-lookup"><span data-stu-id="4f359-218">CPU(s): The amount of processor time that the process has used on all processors, in seconds.</span></span>
  - <span data-ttu-id="4f359-219">ID: идентификатор процесса (PID) процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-219">ID: The process ID (PID) of the process.</span></span>
  - <span data-ttu-id="4f359-220">ProcessName: имя процесса.</span><span class="sxs-lookup"><span data-stu-id="4f359-220">ProcessName: The name of the process.</span></span>
    <span data-ttu-id="4f359-221">Описание понятий, связанных с процессами, см. в центре справки и поддержки, а также в справке диспетчера задач.</span><span class="sxs-lookup"><span data-stu-id="4f359-221">For explanations of the concepts related to processes, see the Glossary in Help and Support Center and the Help for Task Manager.</span></span>
- <span data-ttu-id="4f359-222">Вы также можете использовать встроенные альтернативные представления процессов `Format-Table` , таких как **StartTime** и **Priority** , а также создавать собственные представления.</span><span class="sxs-lookup"><span data-stu-id="4f359-222">You can also use the built-in alternate views of the processes available with `Format-Table`, such as **StartTime** and **Priority** , and you can design your own views.</span></span>

## <span data-ttu-id="4f359-223">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4f359-223">RELATED LINKS</span></span>

[<span data-ttu-id="4f359-224">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="4f359-224">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="4f359-225">Get-Process</span><span class="sxs-lookup"><span data-stu-id="4f359-225">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="4f359-226">Start-Process</span><span class="sxs-lookup"><span data-stu-id="4f359-226">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="4f359-227">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="4f359-227">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="4f359-228">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="4f359-228">Wait-Process</span></span>](Wait-Process.md)

