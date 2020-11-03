---
description: Описывает, как интерпретировать и отформатировать выходные данные удаленных команд.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 14e4f8f2d3edf5c171a8ae743392b23fc0d057f9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232106"
---
# <a name="about-remote-output"></a><span data-ttu-id="2479f-104">Об удаленных выходных данных</span><span class="sxs-lookup"><span data-stu-id="2479f-104">About Remote Output</span></span>

## <a name="short-description"></a><span data-ttu-id="2479f-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2479f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2479f-106">Описывает, как интерпретировать и отформатировать выходные данные удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="2479f-106">Describes how to interpret and format the output of remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="2479f-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2479f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2479f-108">Выходные данные команды, запущенной на удаленном компьютере, могут выглядеть так, как выходные данные одной и той же команды выполняются на локальном компьютере, но существуют некоторые существенные различия.</span><span class="sxs-lookup"><span data-stu-id="2479f-108">The output of a command that was run on a remote computer might look like output of the same command run on a local computer, but there are some significant differences.</span></span>

<span data-ttu-id="2479f-109">В этом разделе объясняется, как интерпретировать, форматировать и отображать выходные данные команд, выполняемых на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="2479f-109">This topic explains how to interpret, format, and display the output of commands that are run on remote computers.</span></span>

## <a name="displaying-the-computer-name"></a><span data-ttu-id="2479f-110">ОТОБРАЖЕНИЕ ИМЕНИ КОМПЬЮТЕРА</span><span class="sxs-lookup"><span data-stu-id="2479f-110">DISPLAYING THE COMPUTER NAME</span></span>

<span data-ttu-id="2479f-111">При использовании командлета Invoke-Command для выполнения команды на удаленном компьютере команда возвращает объект, содержащий имя компьютера, создавшего данные.</span><span class="sxs-lookup"><span data-stu-id="2479f-111">When you use the Invoke-Command cmdlet to run a command on a remote computer, the command returns an object that includes the name of the computer that generated the data.</span></span> <span data-ttu-id="2479f-112">Имя удаленного компьютера хранится в свойстве PSComputerName.</span><span class="sxs-lookup"><span data-stu-id="2479f-112">The remote computer name is stored in the PSComputerName property.</span></span>

<span data-ttu-id="2479f-113">Для многих команд PSComputerName отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2479f-113">For many commands, the PSComputerName is displayed by default.</span></span> <span data-ttu-id="2479f-114">Например, следующая команда выполняет команду Get-Culture на двух удаленных компьютерах, Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="2479f-114">For example, the following command runs a Get-Culture command on two remote computers, Server01 and Server02.</span></span> <span data-ttu-id="2479f-115">Выходные данные, показанные ниже, включают имена удаленных компьютеров, на которых выполнялась команда.</span><span class="sxs-lookup"><span data-stu-id="2479f-115">The output, which appears below, includes the names of the remote computers on which the command ran.</span></span>

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

<span data-ttu-id="2479f-116">Чтобы скрыть свойство PSComputerName, можно использовать параметр Хидекомпутернаме Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="2479f-116">You can use the HideComputerName parameter of Invoke-Command to hide the PSComputerName property.</span></span> <span data-ttu-id="2479f-117">Этот параметр предназначен для команд, собирающих данные только с одного удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="2479f-117">This parameter is designed for commands that collect data from only one remote computer.</span></span>

<span data-ttu-id="2479f-118">Следующая команда выполняет команду Get-Culture на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="2479f-118">The following command runs a Get-Culture command on the Server01 remote computer.</span></span> <span data-ttu-id="2479f-119">Для скрытия свойства PSComputerName и связанных свойств используется параметр Хидекомпутернаме.</span><span class="sxs-lookup"><span data-stu-id="2479f-119">It uses the HideComputerName parameter to hide the PSComputerName property and related properties.</span></span>

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="2479f-120">Можно также отобразить свойство PSComputerName, если оно не отображается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2479f-120">You can also display the PSComputerName property if it is not displayed by default.</span></span>

<span data-ttu-id="2479f-121">Например, следующие команды используют командлет Format-Table для добавления свойства PSComputerName в выходные данные удаленной команды Get-Date.</span><span class="sxs-lookup"><span data-stu-id="2479f-121">For example, the following commands use the Format-Table cmdlet to add the PSComputerName property to the output of a remote Get-Date command.</span></span>

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a><span data-ttu-id="2479f-122">ОТОБРАЖЕНИЕ СВОЙСТВА MACHINENAME</span><span class="sxs-lookup"><span data-stu-id="2479f-122">DISPLAYING THE MACHINENAME PROPERTY</span></span>

<span data-ttu-id="2479f-123">Несколько командлетов, в том числе Get-Process, Get-Service и Get-EventLog, имеют параметр ComputerName, который получает объекты на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2479f-123">Several cmdlets, including Get-Process, Get-Service, and Get-EventLog, have a ComputerName parameter that gets the objects on a remote computer.</span></span>
<span data-ttu-id="2479f-124">Эти командлеты не используют удаленное взаимодействие PowerShell, поэтому их можно использовать даже на компьютерах, которые не настроены для удаленного взаимодействия в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2479f-124">These cmdlets do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="2479f-125">Объекты, возвращаемые этими командлетами, сохраняют имя удаленного компьютера в свойстве MachineName.</span><span class="sxs-lookup"><span data-stu-id="2479f-125">The objects that these cmdlets return store the name of the remote computer in the MachineName property.</span></span> <span data-ttu-id="2479f-126">(Эти объекты не имеют свойства PSComputerName.)</span><span class="sxs-lookup"><span data-stu-id="2479f-126">(These objects do not have a PSComputerName property.)</span></span>

<span data-ttu-id="2479f-127">Например, эта команда получает процесс PowerShell на удаленных компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="2479f-127">For example, this command gets the PowerShell process on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="2479f-128">Отображение по умолчанию не включает свойство MachineName.</span><span class="sxs-lookup"><span data-stu-id="2479f-128">The default display does not include the MachineName property.</span></span>

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

<span data-ttu-id="2479f-129">Для вывода свойства MachineName объектов процесса можно использовать командлет Format-Table.</span><span class="sxs-lookup"><span data-stu-id="2479f-129">You can use the Format-Table cmdlet to display the MachineName property of the process objects.</span></span>

<span data-ttu-id="2479f-130">Например, следующая команда сохраняет процессы в переменной $p, а затем использует оператор конвейера (|) для отправки процессов в $p команде Format-Table.</span><span class="sxs-lookup"><span data-stu-id="2479f-130">For example, the following command saves the processes in the $p variable and then uses a pipeline operator (|) to send the processes in $p to the Format-Table command.</span></span> <span data-ttu-id="2479f-131">Команда использует параметр Property объекта Format-Table для включения свойства MachineName в экран.</span><span class="sxs-lookup"><span data-stu-id="2479f-131">The command uses the Property parameter of Format-Table to include the MachineName property in the display.</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

<span data-ttu-id="2479f-132">Следующая более сложная команда добавляет свойство MachineName к отображению процесса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2479f-132">The following more complex command adds the MachineName property to the default process display.</span></span> <span data-ttu-id="2479f-133">Для указания вычисляемых свойств используются хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="2479f-133">It uses hash tables to specify calculated properties.</span></span> <span data-ttu-id="2479f-134">К счастью, вам не нужно понимать, что его использовать.</span><span class="sxs-lookup"><span data-stu-id="2479f-134">Fortunately, you do not have to understand it to use it.</span></span>

<span data-ttu-id="2479f-135">(Обратите внимание, что Обратная кавычка ['] является символом продолжения.)</span><span class="sxs-lookup"><span data-stu-id="2479f-135">(Note that the backtick [\`] is the continuation character.)</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a><span data-ttu-id="2479f-136">ДЕСЕРИАЛИЗОВАННЫЕ ОБЪЕКТЫ</span><span class="sxs-lookup"><span data-stu-id="2479f-136">DESERIALIZED OBJECTS</span></span>

<span data-ttu-id="2479f-137">При выполнении удаленных команд, которые формируют выходные данные команды, передаются по сети обратно на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="2479f-137">When you run remote commands that generate output, the command output is transmitted across the network back to the local computer.</span></span>

<span data-ttu-id="2479f-138">Так как большинство объектов Microsoft .NET Framework (например, объекты, возвращаемые командлетами PowerShell) не могут передаваться по сети, объекты в реальном времени сериализуются.</span><span class="sxs-lookup"><span data-stu-id="2479f-138">Because most live Microsoft .NET Framework objects (such as the objects that PowerShell cmdlets return) cannot be transmitted over the network, the live objects are "serialized".</span></span> <span data-ttu-id="2479f-139">Иными словами, активные объекты преобразуются в XML-представления объекта и его свойств.</span><span class="sxs-lookup"><span data-stu-id="2479f-139">In other words, the live objects are converted into XML representations of the object and its properties.</span></span> <span data-ttu-id="2479f-140">Затем сериализованный объект на основе XML передается по сети.</span><span class="sxs-lookup"><span data-stu-id="2479f-140">Then, the XML-based serialized object is transmitted across the network.</span></span>

<span data-ttu-id="2479f-141">На локальном компьютере PowerShell получает сериализованный объект на основе XML и десериализует его путем преобразования объекта на основе XML в стандартный объект .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2479f-141">On the local computer, PowerShell receives the XML-based serialized object and "deserializes" it by converting the XML-based object into a standard .NET Framework object.</span></span>

<span data-ttu-id="2479f-142">Однако десериализованный объект не является активным объектом.</span><span class="sxs-lookup"><span data-stu-id="2479f-142">However, the deserialized object is not a live object.</span></span> <span data-ttu-id="2479f-143">Он является моментальным снимком объекта во время его сериализации и содержит свойства, но не имеет методов.</span><span class="sxs-lookup"><span data-stu-id="2479f-143">It is a snapshot of the object at the time that it was serialized, and it includes properties but no methods.</span></span> <span data-ttu-id="2479f-144">Вы можете использовать эти объекты и управлять ими в PowerShell, в том числе передавать их в конвейеры, отображая выбранные свойства и форматировать их.</span><span class="sxs-lookup"><span data-stu-id="2479f-144">You can use and manage these objects in PowerShell, including passing them in pipelines, displaying selected properties, and formatting them.</span></span>

<span data-ttu-id="2479f-145">Большинство десериализованных объектов автоматически отформатированы для показа записями в Types.ps1XML-или Format.ps1XML-файлах.</span><span class="sxs-lookup"><span data-stu-id="2479f-145">Most deserialized objects are automatically formatted for display by entries in the Types.ps1xml or Format.ps1xml files.</span></span> <span data-ttu-id="2479f-146">Однако на локальном компьютере могут отсутствовать файлы форматирования для всех десериализованных объектов, созданных на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2479f-146">However, the local computer might not have formatting files for all of the deserialized objects that were generated on a remote computer.</span></span> <span data-ttu-id="2479f-147">Если объекты не отформатированы, все свойства каждого объекта отображаются в консоли в списке потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="2479f-147">When objects are not formatted, all of the properties of each object appear in the console in a streaming list.</span></span>

<span data-ttu-id="2479f-148">Если объекты не отформатированы автоматически, можно использовать командлеты форматирования, такие как Format-Table или Format-List, для форматирования и вывода выбранных свойств.</span><span class="sxs-lookup"><span data-stu-id="2479f-148">When objects are not formatted automatically, you can use the formatting cmdlets, such as Format-Table or Format-List, to format and display selected properties.</span></span> <span data-ttu-id="2479f-149">Также можно использовать командлет Out-GridView для вывода объектов в таблице.</span><span class="sxs-lookup"><span data-stu-id="2479f-149">Or, you can use the Out-GridView cmdlet to display the objects in a table.</span></span>

<span data-ttu-id="2479f-150">Кроме того, при выполнении команды на удаленном компьютере, использующем командлеты, которых нет на локальном компьютере, объекты, возвращаемые командой, могут быть неправильно отформатированы, так как у вас нет файлов форматирования для этих объектов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2479f-150">Also, if you run a command on a remote computer that uses cmdlets that you do not have on your local computer, the objects that the command returns might not be formatted properly because you do not have the formatting files for those objects on your computer.</span></span> <span data-ttu-id="2479f-151">Чтобы получить данные форматирования с другого компьютера, используйте командлеты Get-FormatData и Export-FormatData.</span><span class="sxs-lookup"><span data-stu-id="2479f-151">To get formatting data from another computer, use the Get-FormatData and Export-FormatData cmdlets.</span></span>

<span data-ttu-id="2479f-152">Некоторые типы объектов, например объекты DirectoryInfo и GUID, преобразуются обратно в динамические объекты при их получении.</span><span class="sxs-lookup"><span data-stu-id="2479f-152">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="2479f-153">Для этих объектов не требуется специальная обработка или форматирование.</span><span class="sxs-lookup"><span data-stu-id="2479f-153">These objects do not need any special handling or formatting.</span></span>

## <a name="ordering-the-results"></a><span data-ttu-id="2479f-154">УПОРЯДОЧИВАНИЕ РЕЗУЛЬТАТОВ</span><span class="sxs-lookup"><span data-stu-id="2479f-154">ORDERING THE RESULTS</span></span>

<span data-ttu-id="2479f-155">Порядок имен компьютеров в параметре ComputerName командлетов определяет порядок, в котором PowerShell подключается к удаленным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="2479f-155">The order of the computer names in the ComputerName parameter of cmdlets determines the order in which PowerShell connects to the remote computers.</span></span> <span data-ttu-id="2479f-156">Однако результаты отображаются в порядке, в котором локальный компьютер получает их, что может отличаться от порядка.</span><span class="sxs-lookup"><span data-stu-id="2479f-156">However, the results appear in the order in which the local computer receives them, which might be a different order.</span></span>

<span data-ttu-id="2479f-157">Чтобы изменить порядок результатов, используйте командлет Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="2479f-157">To change the order of the results, use the Sort-Object cmdlet.</span></span> <span data-ttu-id="2479f-158">Можно выполнить сортировку по свойству PSComputerName или MachineName.</span><span class="sxs-lookup"><span data-stu-id="2479f-158">You can sort on the PSComputerName or MachineName property.</span></span> <span data-ttu-id="2479f-159">Можно также выполнить сортировку по другому свойству объекта, чтобы результаты с разных компьютеров были смешанными.</span><span class="sxs-lookup"><span data-stu-id="2479f-159">You can also sort on another property of the object so that the results from different computers are interspersed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2479f-160">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="2479f-160">SEE ALSO</span></span>

[<span data-ttu-id="2479f-161">about_Remote</span><span class="sxs-lookup"><span data-stu-id="2479f-161">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="2479f-162">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="2479f-162">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="2479f-163">Format-Table</span><span class="sxs-lookup"><span data-stu-id="2479f-163">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="2479f-164">Get-Process</span><span class="sxs-lookup"><span data-stu-id="2479f-164">Get-Process</span></span>](xref:Microsoft.PowerShell.Management.Get-Process)

[<span data-ttu-id="2479f-165">Get-Service</span><span class="sxs-lookup"><span data-stu-id="2479f-165">Get-Service</span></span>](xref:Microsoft.PowerShell.Management.Get-Service)

[<span data-ttu-id="2479f-166">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2479f-166">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="2479f-167">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2479f-167">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

