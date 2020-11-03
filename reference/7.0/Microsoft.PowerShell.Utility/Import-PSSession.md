---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: fafc4da46eb6b6f7cf252d5ca2aa50f6bd42b49f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225558"
---
# <span data-ttu-id="04694-103">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="04694-103">Import-PSSession</span></span>

## <span data-ttu-id="04694-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="04694-104">SYNOPSIS</span></span>
<span data-ttu-id="04694-105">Импортирует команды из другого сеанса в текущий.</span><span class="sxs-lookup"><span data-stu-id="04694-105">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="04694-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04694-106">SYNTAX</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="04694-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04694-107">DESCRIPTION</span></span>

<span data-ttu-id="04694-108">Командлет **Import-PSSession** импортирует команды, такие как командлеты, функции и псевдонимы, из сеанса PSSession на локальном или удаленном компьютере в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-108">The **Import-PSSession** cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span>
<span data-ttu-id="04694-109">Можно импортировать любую команду, которую командлет Get-Command может найти в сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-109">You can import any command that the Get-Command cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="04694-110">Команда **Import-PSSession** используется для импорта команд из настраиваемой оболочки, например оболочки Microsoft Exchange Server, или из сеанса, содержащего модули и оснастки PowerShell, а также другие элементы, которые не находятся в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-110">Use an **Import-PSSession** command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="04694-111">Чтобы импортировать команды, сначала используйте командлет New-PSSession, чтобы создать сеанс PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-111">To import commands, first use the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="04694-112">После этого используйте командлет **Import-PSSession** для импорта команд.</span><span class="sxs-lookup"><span data-stu-id="04694-112">Then, use the **Import-PSSession** cmdlet to import the commands.</span></span>
<span data-ttu-id="04694-113">По умолчанию **Import-PSSession** импортирует все команды, за исключением команд, которые имеют такие же имена, как и команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-113">By default, **Import-PSSession** imports all commands except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="04694-114">Чтобы импортировать все команды, используйте параметр *AllowClobber*.</span><span class="sxs-lookup"><span data-stu-id="04694-114">To import all the commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="04694-115">Импортированные команды можно использовать точно так же, как и любую команду в сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-115">You can use imported commands just as you would use any command in the session.</span></span>
<span data-ttu-id="04694-116">При использовании импортированных команд импортированная часть команды выполняется неявно в сеансе, из которой она была импортирована.</span><span class="sxs-lookup"><span data-stu-id="04694-116">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span>
<span data-ttu-id="04694-117">Однако удаленные операции полностью обрабатываются PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04694-117">However, the remote operations are handled entirely by PowerShell.</span></span>
<span data-ttu-id="04694-118">Вам даже не нужно помнить о них, за исключением того, что нужно поддерживать подключение к другому сеансу (PSSession) открытым.</span><span class="sxs-lookup"><span data-stu-id="04694-118">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span>
<span data-ttu-id="04694-119">Если его закрыть, импортированные команды перестают быть недоступными.</span><span class="sxs-lookup"><span data-stu-id="04694-119">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="04694-120">Поскольку импортированные команды могут выполняться дольше локальных, **Import-PSSession** добавляет в каждую импортированную команду параметр *AsJob*.</span><span class="sxs-lookup"><span data-stu-id="04694-120">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="04694-121">Этот параметр позволяет выполнять команду в качестве фонового задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04694-121">This parameter allows you to run the command as a PowerShell background job.</span></span>
<span data-ttu-id="04694-122">Дополнительные сведения см. в разделе about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="04694-122">For more information, see about_Jobs.</span></span>

<span data-ttu-id="04694-123">При использовании командлета **Import-PSSession** PowerShell добавляет импортированные команды во временный модуль, который существует только в сеансе, и возвращает объект, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="04694-123">When you use **Import-PSSession** , PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span>
<span data-ttu-id="04694-124">Чтобы создать постоянный модуль, который можно использовать в будущих сеансах, используйте командлет Export-PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-124">To create a persistent module that you can use in future sessions, use the Export-PSSession cmdlet.</span></span>

<span data-ttu-id="04694-125">Командлет **Import-PSSession** использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04694-125">The **Import-PSSession** cmdlet uses the implicit remoting feature of PowerShell.</span></span>
<span data-ttu-id="04694-126">При импорте команд в текущий сеанс они выполняются неявно в исходном сеансе или в аналогичном сеансе на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="04694-126">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="04694-127">Начиная с Windows PowerShell 3,0, можно использовать командлет Import-Module для импорта модулей из удаленного сеанса в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-127">Beginning in Windows PowerShell 3.0, you can use the Import-Module cmdlet to import modules from a remote session into the current session.</span></span>
<span data-ttu-id="04694-128">Эта функция использует неявное удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="04694-128">This feature uses implicit remoting.</span></span>
<span data-ttu-id="04694-129">Это эквивалентно использованию **Import-PSSession** для импорта выбранных модулей из удаленного сеанса в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-129">It is equivalent to using **Import-PSSession** to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="04694-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="04694-130">EXAMPLES</span></span>

### <span data-ttu-id="04694-131">Пример 1. импорт всех команд из PSSession</span><span class="sxs-lookup"><span data-stu-id="04694-131">Example 1: Import all commands from a PSSession</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

<span data-ttu-id="04694-132">Эта команда импортирует все команды из PSSession на компьютере Server01 в текущий сеанс, за исключением команд, которые имеют такие же имена, как и команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-132">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="04694-133">Поскольку эта команда не использует параметр *CommandName* , она также импортирует все необходимые для импортированных команд данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="04694-133">Because this command does not use the *CommandName* parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="04694-134">Пример 2. Импорт команд, заканчивающихся заданной строкой</span><span class="sxs-lookup"><span data-stu-id="04694-134">Example 2: Import commands that end with a specific string</span></span>

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

<span data-ttu-id="04694-135">Эти команды импортируют команды, имена которых заканчиваются на "-test", из PSSession в локальный сеанс, а затем показывают, как использовать импортированный командлет.</span><span class="sxs-lookup"><span data-stu-id="04694-135">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="04694-136">Первая команда использует командлет New-PSSession для создания сеанса PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-136">The first command uses the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="04694-137">Он сохраняет PSSession в переменной $S.</span><span class="sxs-lookup"><span data-stu-id="04694-137">It saves the PSSession in the $S variable.</span></span>

<span data-ttu-id="04694-138">Вторая команда использует командлет **Import-PSSession** для импорта команд из PSSession в $S в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-138">The second command uses the **Import-PSSession** cmdlet to import commands from the PSSession in $S into the current session.</span></span>
<span data-ttu-id="04694-139">Она использует параметр *CommandName* , чтобы указать команды с существительным Test, и параметр *FormatTypeName* , чтобы импортировать данные форматирования для команд Test.</span><span class="sxs-lookup"><span data-stu-id="04694-139">It uses the *CommandName* parameter to specify commands with the Test noun and the *FormatTypeName* parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="04694-140">Третья и четвертая команды используют импортированные команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-140">The third and fourth commands use the imported commands in the current session.</span></span>
<span data-ttu-id="04694-141">Поскольку импортированные команды фактически добавляются в текущий сеанс, для их выполнения используется локальный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="04694-141">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span>
<span data-ttu-id="04694-142">Для выполнения импортированной команды не нужно использовать командлет Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="04694-142">You do not need to use the Invoke-Command cmdlet to run an imported command.</span></span>

### <span data-ttu-id="04694-143">Пример 3. импорт командлетов из PSSession</span><span class="sxs-lookup"><span data-stu-id="04694-143">Example 3: Import cmdlets from a PSSession</span></span>

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="04694-144">Этот пример показывает, что импортированные командлеты можно использовать точно так же, как и локальные командлеты.</span><span class="sxs-lookup"><span data-stu-id="04694-144">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="04694-145">Эти команды импортируют командлеты New-Test и Get-Test из PSSession на компьютере Server01 и командлет Set-Test из PSSession на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="04694-145">These commands import the New-Test and Get-Test cmdlets from a PSSession on the Server01 computer and the Set-Test cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="04694-146">Несмотря на то, что командлеты были импортированы из разных сеансов PSSession, можно без ошибок передать объект из одного командлета в другой.</span><span class="sxs-lookup"><span data-stu-id="04694-146">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="04694-147">Пример 4. Запуск импортированной команды в качестве фонового задания</span><span class="sxs-lookup"><span data-stu-id="04694-147">Example 4: Run an imported command as a background job</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

<span data-ttu-id="04694-148">В этом примере показано, как выполнять импортированную команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="04694-148">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="04694-149">Поскольку импортированные команды могут выполняться дольше локальных, **Import-PSSession** добавляет в каждую импортированную команду параметр *AsJob*.</span><span class="sxs-lookup"><span data-stu-id="04694-149">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="04694-150">Параметр *AsJob* позволяет выполнить команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="04694-150">The *AsJob* parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="04694-151">Первая команда создает сеанс PSSession на компьютере Server01 и сохраняет объект PSSession в переменной $S.</span><span class="sxs-lookup"><span data-stu-id="04694-151">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the $S variable.</span></span>

<span data-ttu-id="04694-152">Вторая команда использует **Import-PSSession** для импорта командлетов теста из PSSession в $S в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-152">The second command uses **Import-PSSession** to import the Test cmdlets from the PSSession in $S into the current session.</span></span>

<span data-ttu-id="04694-153">Третья команда использует параметр *AsJob* импортированного командлета New-Test для запуска команды New-Test в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="04694-153">The third command uses the *AsJob* parameter of the imported New-Test cmdlet to run a New-Test command as a background job.</span></span>
<span data-ttu-id="04694-154">Команда сохраняет возвращаемый New-Test объект задания в переменной $batch.</span><span class="sxs-lookup"><span data-stu-id="04694-154">The command saves the job object that New-Test returns in the $batch variable.</span></span>

<span data-ttu-id="04694-155">Четвертая команда использует командлет Receive-Job для получения результатов задания в переменной $batch.</span><span class="sxs-lookup"><span data-stu-id="04694-155">The fourth command uses the Receive-Job cmdlet to get the results of the job in the $batch variable.</span></span>

### <span data-ttu-id="04694-156">Пример 5. импорт командлетов и функций из модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="04694-156">Example 5: Import cmdlets and functions from a PowerShell module</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="04694-157">В этом примере показано, как импортировать командлеты и функции из модуля PowerShell на удаленном компьютере в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-157">This example shows how to import the cmdlets and functions from a PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="04694-158">Первая команда создает сеанс PSSession на компьютере Server01 и сохраняет его в переменной $S.</span><span class="sxs-lookup"><span data-stu-id="04694-158">The first command creates a PSSession on the Server01 computer and saves it in the $S variable.</span></span>

<span data-ttu-id="04694-159">Вторая команда использует командлет **Invoke-Command** для выполнения команды Import-Module в сеансе PSSession в $S.</span><span class="sxs-lookup"><span data-stu-id="04694-159">The second command uses the **Invoke-Command** cmdlet to run an Import-Module command in the PSSession in $S.</span></span>

<span data-ttu-id="04694-160">Как правило, модуль будет добавлен во все сеансы командой **Import-Module** в профиле PowerShell, но профили не будут выполняться в PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-160">Typically, the module would be added to all sessions by an **Import-Module** command in a PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="04694-161">Третья команда использует параметр *module*  команды **Import-PSSession** для импорта командлетов и функций в модуль в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-161">The third command uses the *Module*  parameter of **Import-PSSession** to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="04694-162">Пример 6. Создание модуля во временном файле</span><span class="sxs-lookup"><span data-stu-id="04694-162">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="04694-163">В этом примере показано, что **Import-PSSession** создает модуль во временном файле на диске.</span><span class="sxs-lookup"><span data-stu-id="04694-163">This example shows that **Import-PSSession** creates a module in a temporary file on disk.</span></span>
<span data-ttu-id="04694-164">В нем также показано, что все команды преобразуются в функции перед их импортом в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-164">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="04694-165">Команда использует командлет **Import-PSSession** для импорта командлета Get-Date и функции сеарчхелп в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-165">The command uses the **Import-PSSession** cmdlet to import a Get-Date cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="04694-166">Командлет **Import-PSSession** возвращает объект **PSModuleInfo** , представляющий временный модуль.</span><span class="sxs-lookup"><span data-stu-id="04694-166">The **Import-PSSession** cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span>
<span data-ttu-id="04694-167">Значение **Path** свойства показывает, что **Import-PSSession** создал во временной папке файл модуля сценариев (PSM1).</span><span class="sxs-lookup"><span data-stu-id="04694-167">The value of the **Path** property shows that **Import-PSSession** created a script module (.psm1) file in a temporary location.</span></span>
<span data-ttu-id="04694-168">Свойство **ExportedFunctions** показывает, что командлет **Get-Date** и функция SearchHelp были импортированы как функции.</span><span class="sxs-lookup"><span data-stu-id="04694-168">The **ExportedFunctions** property shows that the **Get-Date** cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="04694-169">Пример 7. выполнение команды, скрытой импортированной командой</span><span class="sxs-lookup"><span data-stu-id="04694-169">Example 7: Run a command that is hidden by an imported command</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

<span data-ttu-id="04694-170">В этом примере показано, как выполнить команду, скрытую импортированной командой.</span><span class="sxs-lookup"><span data-stu-id="04694-170">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="04694-171">Первая команда импортирует командлет Get-Date из PSSession в переменной $S.</span><span class="sxs-lookup"><span data-stu-id="04694-171">The first command imports a Get-Date cmdlet from the PSSession in the $S variable.</span></span>
<span data-ttu-id="04694-172">Поскольку текущий сеанс включает в себя командлет **Get-Date** , в команде необходимо указать параметр *AllowClobber*.</span><span class="sxs-lookup"><span data-stu-id="04694-172">Because the current session includes a **Get-Date** cmdlet, the *AllowClobber* parameter is required in the command.</span></span>

<span data-ttu-id="04694-173">Вторая команда использует параметр **ALL** командлета Get-Command для получения всех команд **Get-Date** в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-173">The second command uses the **All** parameter of the Get-Command cmdlet to get all **Get-Date** commands in the current session.</span></span>
<span data-ttu-id="04694-174">Выходные данные показывают, что сеанс включает в себя исходный командлет **Get-Date** и функцию **Get-Date**.</span><span class="sxs-lookup"><span data-stu-id="04694-174">The output shows that the session includes the original **Get-Date** cmdlet and a **Get-Date** function.</span></span>
<span data-ttu-id="04694-175">Функция **Get-Date** запускает импортированный командлет **Get-Date** в сеансе PSSession в $S.</span><span class="sxs-lookup"><span data-stu-id="04694-175">The **Get-Date** function runs the imported **Get-Date** cmdlet in the PSSession in $S.</span></span>

<span data-ttu-id="04694-176">Третья команда выполняет команду **Get-Date**.</span><span class="sxs-lookup"><span data-stu-id="04694-176">The third command runs a **Get-Date** command.</span></span>
<span data-ttu-id="04694-177">Поскольку функции имеют приоритет над командлетами, PowerShell выполняет импортированную функцию **Get-Date** , которая возвращает Юлианскую дату.</span><span class="sxs-lookup"><span data-stu-id="04694-177">Because functions take precedence over cmdlets, PowerShell runs the imported **Get-Date** function, which returns a Julian date.</span></span>

<span data-ttu-id="04694-178">Четвертая и пятая команды показывают, как использовать полное имя для выполнения команды, которая скрыта импортированной командой.</span><span class="sxs-lookup"><span data-stu-id="04694-178">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="04694-179">Четвертая команда возвращает имя оснастки PowerShell, которая добавила исходный командлет **Get-Date** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-179">The fourth command gets the name of the PowerShell snap-in that added the original **Get-Date** cmdlet to the current session.</span></span>

<span data-ttu-id="04694-180">Пятая команда использует полное имя командлета **Get-Date** , учитывающее оснастку, для запуска команды **Get-Date**.</span><span class="sxs-lookup"><span data-stu-id="04694-180">The fifth command uses the snap-in-qualified name of the **Get-Date** cmdlet to run a **Get-Date** command.</span></span>

<span data-ttu-id="04694-181">Дополнительные сведения о приоритете команд и скрытых командах см. в разделе about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="04694-181">For more information about command precedence and hidden commands, see about_Command_Precedence.</span></span>

### <span data-ttu-id="04694-182">Пример 8. Импорт команд с определенной строкой в именах</span><span class="sxs-lookup"><span data-stu-id="04694-182">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

<span data-ttu-id="04694-183">Эта команда импортирует команды, имена которых включают элемент из PSSession в $S.</span><span class="sxs-lookup"><span data-stu-id="04694-183">This command imports commands whose names include Item from the PSSession in $S.</span></span>
<span data-ttu-id="04694-184">Так как команда содержит параметр *CommandName* , но не параметр *форматтипедата* , импортируется только команда.</span><span class="sxs-lookup"><span data-stu-id="04694-184">Because the command includes the *CommandName* parameter but not the *FormatTypeData* parameter, only the command is imported.</span></span>

<span data-ttu-id="04694-185">Воспользуйтесь этой командой при использовании **Import-PSSession** для выполнения команды на удаленном компьютере, когда в текущем сеансе уже имеются данные форматирования для этой команды.</span><span class="sxs-lookup"><span data-stu-id="04694-185">Use this command when you are using **Import-PSSession** to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="04694-186">Пример 9. Использование параметра module для определения команд, импортированных в сеанс</span><span class="sxs-lookup"><span data-stu-id="04694-186">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

<span data-ttu-id="04694-187">Эта команда показывает, как использовать параметр *module* командлета **Get-Command** , чтобы узнать, какие команды были импортированы в сеанс с помощью команды **Import-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="04694-187">This command shows how to use the *Module* parameter of **Get-Command** to find out which commands were imported into the session by an **Import-PSSession** command.</span></span>

<span data-ttu-id="04694-188">Первая команда использует командлет **Import-PSSession** для импорта команд, имена которых содержат "BITS", из сеанса PSSession в переменной $S.</span><span class="sxs-lookup"><span data-stu-id="04694-188">The first command uses the **Import-PSSession** cmdlet to import commands whose names include "bits" from the PSSession in the $S variable.</span></span>
<span data-ttu-id="04694-189">Команда **Import-PSSession** возвращает временный модуль и сохраняет его в переменной $m.</span><span class="sxs-lookup"><span data-stu-id="04694-189">The **Import-PSSession** command returns a temporary module, and the command saves the module in the $m variable.</span></span>

<span data-ttu-id="04694-190">Вторая команда использует командлет Get-Command для получения команд, экспортируемых модулем в переменной $M.</span><span class="sxs-lookup"><span data-stu-id="04694-190">The second command uses the Get-Command cmdlet to get the commands that are exported by the module in the $M variable.</span></span>

<span data-ttu-id="04694-191">Параметр *Module* принимает строковое значение, которое предназначено для имени модуля.</span><span class="sxs-lookup"><span data-stu-id="04694-191">The *Module* parameter takes a string value, which is designed for the module name.</span></span>
<span data-ttu-id="04694-192">Однако при отправке объекта модуля PowerShell использует метод **ToString** для объекта Module, который возвращает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="04694-192">However, when you submit a module object, PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="04694-193">Команда **Get-Command** эквивалентна `Get-Command $M.Name` ".</span><span class="sxs-lookup"><span data-stu-id="04694-193">The **Get-Command** command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="04694-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04694-194">PARAMETERS</span></span>

### <span data-ttu-id="04694-195">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="04694-195">-AllowClobber</span></span>

<span data-ttu-id="04694-196">Указывает, что этот командлет импортирует указанные команды, даже если они имеют те же имена, что и команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-196">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="04694-197">При импорте команды с таким же именем, что и у команды в текущем сеансе, импортированная команда скрывает или заменяет собой исходную команду.</span><span class="sxs-lookup"><span data-stu-id="04694-197">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span>
<span data-ttu-id="04694-198">Дополнительные сведения см. в разделе about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="04694-198">For more information, see about_Command_Precedence.</span></span>

<span data-ttu-id="04694-199">По умолчанию **Import-PSSession** не импортирует команды, которые имеют имя, совпадающее с именем команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-199">By default, **Import-PSSession** does not import commands that have the same name as commands in the current session.</span></span>

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

### <span data-ttu-id="04694-200">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="04694-200">-ArgumentList</span></span>

<span data-ttu-id="04694-201">Задает массив команд, полученный в результате использования заданных аргументов (значений параметров).</span><span class="sxs-lookup"><span data-stu-id="04694-201">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="04694-202">Например, чтобы импортировать вариант команды Get-Item в сертификате (CERT:) диск в PSSession в $S введите `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="04694-202">For instance, to import the variant of the Get-Item command in the certificate (Cert:) drive in the PSSession in $S, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-203">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="04694-203">-Certificate</span></span>

<span data-ttu-id="04694-204">Задает сертификат клиента, который используется для подписи файлов формата (\*.Format.ps1xml) или файлов модуля сценариев (PSM1) во временном модуле, создаваемом **Import-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="04694-204">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that **Import-PSSession** creates.</span></span>

<span data-ttu-id="04694-205">Введите переменную, которая содержит сертификат, или команду или выражение, которое возвращает сертификат.</span><span class="sxs-lookup"><span data-stu-id="04694-205">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="04694-206">Чтобы найти сертификат, используйте командлет Get-PfxCertificate или используйте командлет Get-ChildItem в сертификате (CERT:). диск.</span><span class="sxs-lookup"><span data-stu-id="04694-206">To find a certificate, use the Get-PfxCertificate cmdlet or use the Get-ChildItem cmdlet in the Certificate (Cert:) drive.</span></span>
<span data-ttu-id="04694-207">Если сертификат недопустимый или не имеет достаточных полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="04694-207">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-208">-CommandName</span><span class="sxs-lookup"><span data-stu-id="04694-208">-CommandName</span></span>

<span data-ttu-id="04694-209">Задает команды с указанными именами или шаблонами имен.</span><span class="sxs-lookup"><span data-stu-id="04694-209">Specifies commands with the specified names or name patterns.</span></span>
<span data-ttu-id="04694-210">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="04694-210">Wildcards are permitted.</span></span>
<span data-ttu-id="04694-211">Используйте *CommandName* или его псевдоним, *имя*.</span><span class="sxs-lookup"><span data-stu-id="04694-211">Use *CommandName* or its alias, *Name*.</span></span>

<span data-ttu-id="04694-212">По умолчанию **Import-PSSession** импортирует все команды из сеанса, за исключением команд, которые имеют такие же имена, как и команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-212">By default, **Import-PSSession** imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="04694-213">Это предотвращает скрытие или замену команд в текущем сеансе импортированными командами.</span><span class="sxs-lookup"><span data-stu-id="04694-213">This prevents imported commands from hiding or replacing commands in the session.</span></span>
<span data-ttu-id="04694-214">Чтобы импортировать все команды, даже те, которые скрыты или заменены другими командами, используйте параметр *AllowClobber*.</span><span class="sxs-lookup"><span data-stu-id="04694-214">To import all commands, even those that hide or replace other commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="04694-215">При использовании параметра *CommandName* файлы форматирования для команд не импортируются, пока не будет задан параметр *FormatTypeName*.</span><span class="sxs-lookup"><span data-stu-id="04694-215">If you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>
<span data-ttu-id="04694-216">Аналогично, если вы используете параметр *FormatTypeName* , команды не импортируются, пока не будет задан параметр *CommandName*.</span><span class="sxs-lookup"><span data-stu-id="04694-216">Similarly, if you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-217">-CommandType</span><span class="sxs-lookup"><span data-stu-id="04694-217">-CommandType</span></span>

<span data-ttu-id="04694-218">Указывает тип командных объектов.</span><span class="sxs-lookup"><span data-stu-id="04694-218">Specifies the type of command objects.</span></span>
<span data-ttu-id="04694-219">Значение по умолчанию — Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="04694-219">The default value is Cmdlet.</span></span>
<span data-ttu-id="04694-220">Используйте параметр *CommandType* или его псевдоним *Type*.</span><span class="sxs-lookup"><span data-stu-id="04694-220">Use *CommandType* or its alias, *Type*.</span></span>
<span data-ttu-id="04694-221">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="04694-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="04694-222">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="04694-222">Alias.</span></span>
<span data-ttu-id="04694-223">Псевдонимы PowerShell в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-223">The PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="04694-224">Все.</span><span class="sxs-lookup"><span data-stu-id="04694-224">All.</span></span>
<span data-ttu-id="04694-225">Командлеты и функции в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-225">The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="04694-226">приложение.</span><span class="sxs-lookup"><span data-stu-id="04694-226">Application.</span></span>
<span data-ttu-id="04694-227">Все файлы, кроме файлов PowerShell, в путях, указанных в переменной среды PATH ($env:p ь) в удаленном сеансе, включая txt, exe и DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="04694-227">All the files other than PowerShell files in the paths that are listed in the Path environment variable ($env:path) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="04694-228">Командлет.</span><span class="sxs-lookup"><span data-stu-id="04694-228">Cmdlet.</span></span>
<span data-ttu-id="04694-229">Командлеты в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-229">The cmdlets in the remote session.</span></span>
<span data-ttu-id="04694-230">Значение по умолчанию — "Cmdlet".</span><span class="sxs-lookup"><span data-stu-id="04694-230">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="04694-231">Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="04694-231">ExternalScript.</span></span>
<span data-ttu-id="04694-232">PS1-файлы в путях, указанных в переменной среды Path ($env:путь) в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-232">The .ps1 files in the paths listed in the Path environment variable ($env:path) in the remote session.</span></span>
- <span data-ttu-id="04694-233">Фильтр и функция.</span><span class="sxs-lookup"><span data-stu-id="04694-233">Filter and Function.</span></span>
<span data-ttu-id="04694-234">Функции PowerShell в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-234">The PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="04694-235">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="04694-235">Script.</span></span>
<span data-ttu-id="04694-236">Блоки сценариев в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-236">The script blocks in the remote session.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-237">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="04694-237">-DisableNameChecking</span></span>

<span data-ttu-id="04694-238">Указывает, что этот командлет подавляет сообщение, выдающее предупреждение при импорте командлета или функции, имя которой включает неутвержденную команду или запрещенный символ.</span><span class="sxs-lookup"><span data-stu-id="04694-238">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="04694-239">По умолчанию, когда импортируемый модуль экспортирует командлеты или функции с неутвержденными командами в именах, PowerShell выводит следующее предупреждающее сообщение:</span><span class="sxs-lookup"><span data-stu-id="04694-239">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the PowerShell displays the following warning message:</span></span>

<span data-ttu-id="04694-240">"Внимание! некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="04694-240">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span>
<span data-ttu-id="04694-241">Используйте параметр Verbose, чтобы получить дополнительные сведения, или введите Get-Verb, чтобы просмотреть список утвержденных глаголов".</span><span class="sxs-lookup"><span data-stu-id="04694-241">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs."</span></span>

<span data-ttu-id="04694-242">Это сообщение является всего лишь предупреждением.</span><span class="sxs-lookup"><span data-stu-id="04694-242">This message is only a warning.</span></span>
<span data-ttu-id="04694-243">Импорт осуществляется для всего модуля, включая недопустимые команды.</span><span class="sxs-lookup"><span data-stu-id="04694-243">The complete module is still imported, including the non-conforming commands.</span></span>
<span data-ttu-id="04694-244">Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.</span><span class="sxs-lookup"><span data-stu-id="04694-244">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="04694-245">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="04694-245">-FormatTypeName</span></span>

<span data-ttu-id="04694-246">Задает инструкции по форматированию для указанных Microsoft .NET типов платформы.</span><span class="sxs-lookup"><span data-stu-id="04694-246">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="04694-247">Введите имена типов.</span><span class="sxs-lookup"><span data-stu-id="04694-247">Enter the type names.</span></span>
<span data-ttu-id="04694-248">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="04694-248">Wildcards are permitted.</span></span>

<span data-ttu-id="04694-249">Значением этого параметра должно быть имя типа, возвращаемого командой Get-FormatData в сеансе, из которого команда импортируется.</span><span class="sxs-lookup"><span data-stu-id="04694-249">The value of this parameter must be the name of a type that is returned by a Get-FormatData command in the session from which the commands are being imported.</span></span>
<span data-ttu-id="04694-250">Чтобы получить все данные форматирования в удаленном сеансе, введите \*.</span><span class="sxs-lookup"><span data-stu-id="04694-250">To get all of the formatting data in the remote session, type \*.</span></span>

<span data-ttu-id="04694-251">Если команда не содержит ни параметр *CommandName* , ни *FormatTypeName* , командлет Import **-PSSession** импортирует инструкции форматирования для всех типов .NET Framework, возвращаемых командой **Get-FormatData** в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-251">If the command does not include either the *CommandName* or *FormatTypeName* parameter, **Import-PSSession** imports formatting instructions for all .NET Framework types returned by a **Get-FormatData** command in the remote session.</span></span>

<span data-ttu-id="04694-252">Если вы используете параметр *FormatTypeName* , команды не импортируются, пока не будет задан параметр *CommandName*.</span><span class="sxs-lookup"><span data-stu-id="04694-252">If you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

<span data-ttu-id="04694-253">Аналогично, при использовании параметра *CommandName* файлы форматирования для команд не импортируются, пока не будет задан параметр *FormatTypeName*.</span><span class="sxs-lookup"><span data-stu-id="04694-253">Similarly, if you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-254">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="04694-254">-FullyQualifiedModule</span></span>

<span data-ttu-id="04694-255">Задает модули с именами, указанными в форме объектов **ModuleSpecification** (описанных в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290) в библиотеке MSDN).</span><span class="sxs-lookup"><span data-stu-id="04694-255">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library).</span></span>
<span data-ttu-id="04694-256">Например, параметр *FullyQualifiedModule* принимает имя модуля, указанное в формате @ {ModuleName = "ModuleName"; ", ИД =" version_number "} или @ {ModuleName =" ModuleName "; "ИД" = "version_number"; GUID = "GUID"}.</span><span class="sxs-lookup"><span data-stu-id="04694-256">For example, the *FullyQualifiedModule* parameter accepts a module name that is specified in the format @{ModuleName = "modulename"; ModuleVersion = "version_number"} or @{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.</span></span>
<span data-ttu-id="04694-257">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="04694-257">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="04694-258">Нельзя указать параметр *FullyQualifiedModule* в той же команде, что и параметр *module* ; два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="04694-258">You cannot specify the *FullyQualifiedModule* parameter in the same command as a *Module* parameter; the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-259">-Module</span><span class="sxs-lookup"><span data-stu-id="04694-259">-Module</span></span>

<span data-ttu-id="04694-260">Указывает и массив команд в оснастках и модулях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04694-260">Specifies and array of commands in the PowerShell snap-ins and modules.</span></span>
<span data-ttu-id="04694-261">Введите имена оснасток и модулей.</span><span class="sxs-lookup"><span data-stu-id="04694-261">Enter the snap-in and module names.</span></span>
<span data-ttu-id="04694-262">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="04694-262">Wildcards are not permitted.</span></span>

<span data-ttu-id="04694-263">**Import-PSSession** не может импортировать поставщиков из оснастки.</span><span class="sxs-lookup"><span data-stu-id="04694-263">**Import-PSSession** cannot import providers from a snap-in.</span></span>

<span data-ttu-id="04694-264">Дополнительные сведения см. в статьях about_PSSnapins и [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="04694-264">For more information, see about_PSSnapins and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-265">— Префикс</span><span class="sxs-lookup"><span data-stu-id="04694-265">-Prefix</span></span>

<span data-ttu-id="04694-266">Задает префикс для существительных в именах импортированных команд.</span><span class="sxs-lookup"><span data-stu-id="04694-266">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="04694-267">Используйте этот параметр, чтобы избежать конфликтов имен, которые могут возникать, когда разные команды в сеансе имеют одинаковое имя.</span><span class="sxs-lookup"><span data-stu-id="04694-267">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="04694-268">Например, если указать префикс Remote, а затем импортировать командлет Get-Date, то этот командлет будет известен в сеансе как Get-Ремотедате и не будет путать с исходным командлетом **Get-Date** .</span><span class="sxs-lookup"><span data-stu-id="04694-268">For instance, if you specify the prefix Remote and then import a Get-Date cmdlet, the cmdlet is known in the session as Get-RemoteDate, and it is not confused with the original **Get-Date** cmdlet.</span></span>

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

### <span data-ttu-id="04694-269">-Session</span><span class="sxs-lookup"><span data-stu-id="04694-269">-Session</span></span>

<span data-ttu-id="04694-270">Указывает **сеанс PSSession** , из которого импортируются командлеты.</span><span class="sxs-lookup"><span data-stu-id="04694-270">Specifies the **PSSession** from which the cmdlets are imported.</span></span>
<span data-ttu-id="04694-271">Введите переменную, которая содержит объект сеанса, или команду, которая получает объект сеанса, например New-PSSession или Get-PSSession команду.</span><span class="sxs-lookup"><span data-stu-id="04694-271">Enter a variable that contains a session object or a command that gets a session object, such as a New-PSSession or Get-PSSession command.</span></span>
<span data-ttu-id="04694-272">Можно указать только один сеанс.</span><span class="sxs-lookup"><span data-stu-id="04694-272">You can specify only one session.</span></span>
<span data-ttu-id="04694-273">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="04694-273">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04694-274">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="04694-274">CommonParameters</span></span>

<span data-ttu-id="04694-275">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04694-275">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04694-276">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="04694-276">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04694-277">Входные данные</span><span class="sxs-lookup"><span data-stu-id="04694-277">INPUTS</span></span>

### <span data-ttu-id="04694-278">Нет</span><span class="sxs-lookup"><span data-stu-id="04694-278">None</span></span>

<span data-ttu-id="04694-279">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="04694-279">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="04694-280">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="04694-280">OUTPUTS</span></span>

### <span data-ttu-id="04694-281">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="04694-281">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="04694-282">Командлет **Import-PSSession** возвращает тот же объект модуля, который New-Module и Get-Module вернул.</span><span class="sxs-lookup"><span data-stu-id="04694-282">**Import-PSSession** returns the same module object that New-Module and Get-Module cmdlets return.</span></span>
<span data-ttu-id="04694-283">Однако импортированный модуль является временным и существует только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="04694-283">However, the imported module is temporary and exists only in the current session.</span></span>
<span data-ttu-id="04694-284">Чтобы создать постоянный модуль на диске, используйте командлет Export-PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-284">To create a permanent module on disk, use the Export-PSSession cmdlet.</span></span>

## <span data-ttu-id="04694-285">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="04694-285">NOTES</span></span>

* <span data-ttu-id="04694-286">**Import-PSSession** основывается на инфраструктуре удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04694-286">**Import-PSSession** relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="04694-287">Для использования этого командлета компьютер должен быть настроен на удаленное взаимодействие WS-Management.</span><span class="sxs-lookup"><span data-stu-id="04694-287">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="04694-288">Дополнительные сведения см. в разделе about_Remote и about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="04694-288">For more information, see about_Remote and about_Remote_Requirements.</span></span>
* <span data-ttu-id="04694-289">**Import-PSSession** не импортирует переменные или поставщики PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04694-289">**Import-PSSession** does not import variables or PowerShell providers.</span></span>
* <span data-ttu-id="04694-290">При импорте команд, которые имеют те же имена, что и команды в текущем сеансе, импортированные команды в сеансе могут скрывать псевдонимы, функции и командлеты, а также заменять функции и переменные.</span><span class="sxs-lookup"><span data-stu-id="04694-290">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="04694-291">Во избежание конфликтов имен используйте параметр *Prefix*.</span><span class="sxs-lookup"><span data-stu-id="04694-291">To prevent name conflicts, use the *Prefix* parameter.</span></span> <span data-ttu-id="04694-292">Дополнительные сведения см. в разделе about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="04694-292">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="04694-293">**Import-PSSession** преобразует все команды в функции перед их импортом.</span><span class="sxs-lookup"><span data-stu-id="04694-293">**Import-PSSession** converts all commands into functions before it imports them.</span></span> <span data-ttu-id="04694-294">В результате импортированные команды работают немного иначе, чем если бы они сохранили свой исходный тип команды.</span><span class="sxs-lookup"><span data-stu-id="04694-294">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="04694-295">Например, если импортировать командлет из PSSession и затем импортировать командлет с таким же именем из модуля или оснастки, импортированный из PSSession командлет всегда выполняется по умолчанию, поскольку функции имеют приоритет над командлетами.</span><span class="sxs-lookup"><span data-stu-id="04694-295">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="04694-296">И наоборот, если импортировать псевдоним в сеанс, где уже есть псевдоним с таким же именем, всегда используется исходный псевдоним, поскольку псевдонимы имеют приоритет над функциями.</span><span class="sxs-lookup"><span data-stu-id="04694-296">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="04694-297">Дополнительные сведения см. в разделе about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="04694-297">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="04694-298">**Import-PSSession** использует командлет Write-Progress для просмотра хода выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="04694-298">**Import-PSSession** uses the Write-Progress cmdlet to display the progress of the command.</span></span> <span data-ttu-id="04694-299">Во время выполнения команды может отображаться индикатор выполнения .</span><span class="sxs-lookup"><span data-stu-id="04694-299">You might see the progress bar while the command is running.</span></span>
* <span data-ttu-id="04694-300">Чтобы найти команды для импорта, **Import-PSSession** использует командлет Invoke-Command для выполнения команды Get-Command в сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="04694-300">To find the commands to import, **Import-PSSession** uses the Invoke-Command cmdlet to run a Get-Command command in the PSSession.</span></span> <span data-ttu-id="04694-301">Чтобы получить данные форматирования для команд, используется командлет Get-FormatData.</span><span class="sxs-lookup"><span data-stu-id="04694-301">To get formatting data for the commands, it uses the Get-FormatData cmdlet.</span></span> <span data-ttu-id="04694-302">При выполнении команды **Import-PSSession** могут отображаться сообщения об ошибках из этих командлетов.</span><span class="sxs-lookup"><span data-stu-id="04694-302">You might see error messages from these cmdlets when you run an **Import-PSSession** command.</span></span> <span data-ttu-id="04694-303">Кроме того, командлет **Import-PSSession** не может импортировать команды из PSSession, не включающего в себя Get-Command, Get-FormatData, Select-Object и Get-Help.</span><span class="sxs-lookup"><span data-stu-id="04694-303">Also, **Import-PSSession** cannot import commands from a PSSession that does not include the Get-Command, Get-FormatData, Select-Object, and Get-Help cmdlets.</span></span>
* <span data-ttu-id="04694-304">Импортированные команды имеют те же ограничения, что и другие удаленные команды, включая невозможность запуска программы с пользовательским интерфейсом, например "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="04694-304">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
* <span data-ttu-id="04694-305">Так как профили PowerShell не выполняются в PSSession, команды, которые профиль добавляет в сеанс, недоступны для **импорта-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="04694-305">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to **Import-PSSession**.</span></span> <span data-ttu-id="04694-306">Для импорта команд из профиля используйте команду Invoke-Command, чтобы вручную запустить профиль в PSSession перед импортом команд.</span><span class="sxs-lookup"><span data-stu-id="04694-306">To import commands from a profile, use an Invoke-Command command to run the profile in the PSSession manually before importing commands.</span></span>
* <span data-ttu-id="04694-307">Временный модуль, создаваемый **Import-PSSession** , может включать в себя файл форматирования, даже если команда не импортирует данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="04694-307">The temporary module that **Import-PSSession** creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="04694-308">Если команда не импортирует данные форматирования, все создаваемые файлы форматирования не будут содержать данные форматирования.</span><span class="sxs-lookup"><span data-stu-id="04694-308">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
* <span data-ttu-id="04694-309">Для использования **Import-PSSession** политика выполнения в текущем сеансе должна отличаться от Restricted и AllSigned, так как создаваемый **Import-PSSession** временный модуль содержит неподписанные файлы сценариев, которые запрещены в этих политиках.</span><span class="sxs-lookup"><span data-stu-id="04694-309">To use **Import-PSSession** , the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that **Import-PSSession** creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="04694-310">Чтобы использовать командлет **Import-PSSession** без изменения политики выполнения для локального компьютера, используйте параметр *Scope* из Set-ExecutionPolicy, чтобы задать менее ограниченную политику выполнения для одного процесса.</span><span class="sxs-lookup"><span data-stu-id="04694-310">To use **Import-PSSession** without changing the execution policy for the local computer, use the *Scope* parameter of Set-ExecutionPolicy to set a less restrictive execution policy for a single process.</span></span>
* <span data-ttu-id="04694-311">В Windows PowerShell 2.0 разделы справки для команд, которые импортируются из другого сеанса, не включают префикс, назначенный с помощью параметра *Prefix*.</span><span class="sxs-lookup"><span data-stu-id="04694-311">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the *Prefix* parameter.</span></span> <span data-ttu-id="04694-312">Чтобы получить справку для импортированной команды Windows PowerShell 2.0, используйте исходное имя команды (без префикса).</span><span class="sxs-lookup"><span data-stu-id="04694-312">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="04694-313">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="04694-313">RELATED LINKS</span></span>

[<span data-ttu-id="04694-314">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="04694-314">Export-PSSession</span></span>](Export-PSSession.md)
