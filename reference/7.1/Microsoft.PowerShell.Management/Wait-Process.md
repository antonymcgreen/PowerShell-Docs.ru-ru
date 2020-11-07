---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 2d991ec8e992d98425cf72f7e63e0f7f6e2089c0
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345754"
---
# <span data-ttu-id="a86eb-103">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-103">Wait-Process</span></span>

## <span data-ttu-id="a86eb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a86eb-104">SYNOPSIS</span></span>
<span data-ttu-id="a86eb-105">Ожидает остановки процессов, прежде чем принимать дополнительный ввод.</span><span class="sxs-lookup"><span data-stu-id="a86eb-105">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="a86eb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a86eb-106">SYNTAX</span></span>

### <span data-ttu-id="a86eb-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a86eb-107">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a86eb-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a86eb-108">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a86eb-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="a86eb-109">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="a86eb-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a86eb-110">DESCRIPTION</span></span>

<span data-ttu-id="a86eb-111">Командлет **Wait-Process** ожидает остановки одного или нескольких запущенных процессов перед приемом входных данных.</span><span class="sxs-lookup"><span data-stu-id="a86eb-111">The **Wait-Process** cmdlet waits for one or more running processes to be stopped before accepting input.</span></span>
<span data-ttu-id="a86eb-112">В консоли PowerShell этот командлет подавляет командную строку до тех пор, пока процессы не будут остановлены.</span><span class="sxs-lookup"><span data-stu-id="a86eb-112">In the PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span>
<span data-ttu-id="a86eb-113">Можно указать процесс по имени или ИДЕНТИФИКАТОРу процесса (PID) или передать объект процесса в **Wait-Process**.</span><span class="sxs-lookup"><span data-stu-id="a86eb-113">You can specify a process by process name or process ID (PID), or pipe a process object to **Wait-Process**.</span></span>

<span data-ttu-id="a86eb-114">**Wait-Process** работает только с процессами, запущенными на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a86eb-114">**Wait-Process** works only on processes running on the local computer.</span></span>

## <span data-ttu-id="a86eb-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="a86eb-115">EXAMPLES</span></span>

### <span data-ttu-id="a86eb-116">Пример 1. завершение процесса и ожидание</span><span class="sxs-lookup"><span data-stu-id="a86eb-116">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="a86eb-117">В этом примере останавливается процесс «Блокнот», а затем происходит ожидание остановки процесса, прежде чем продолжить выполнение следующей команды.</span><span class="sxs-lookup"><span data-stu-id="a86eb-117">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="a86eb-118">Первая команда использует командлет **Get-Process** для получения идентификатора процесса Блокнота.</span><span class="sxs-lookup"><span data-stu-id="a86eb-118">The first command uses the **Get-Process** cmdlet to get the ID of the Notepad process.</span></span>
<span data-ttu-id="a86eb-119">Идентификатор сохраняется в переменной $nid.</span><span class="sxs-lookup"><span data-stu-id="a86eb-119">It stores the ID in the $nid variable.</span></span>

<span data-ttu-id="a86eb-120">Вторая команда использует командлет Stop-Process для завершения процесса с ИДЕНТИФИКАТОРом, хранящимся в $nid.</span><span class="sxs-lookup"><span data-stu-id="a86eb-120">The second command uses the Stop-Process cmdlet to stop the process with the ID stored in $nid.</span></span>

<span data-ttu-id="a86eb-121">Третья команда использует **Wait-Process** для ожидания остановки процесса Блокнота.</span><span class="sxs-lookup"><span data-stu-id="a86eb-121">The third command uses **Wait-Process** to wait until the Notepad process is stopped.</span></span>
<span data-ttu-id="a86eb-122">Для идентификации процесса в нем используется параметр *идентификатора* **ожидания процесса** .</span><span class="sxs-lookup"><span data-stu-id="a86eb-122">It uses the *Id* parameter of **Wait-Process** to identify the process.</span></span>

### <span data-ttu-id="a86eb-123">Пример 2. Указание процесса</span><span class="sxs-lookup"><span data-stu-id="a86eb-123">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="a86eb-124">Эти команды демонстрируют три разных способа указания процесса **ожидания обработки**.</span><span class="sxs-lookup"><span data-stu-id="a86eb-124">These commands show three different methods of specifying a process to **Wait-Process**.</span></span>
<span data-ttu-id="a86eb-125">Первая команда получает процесс блокнота и сохраняет его в переменной $p.</span><span class="sxs-lookup"><span data-stu-id="a86eb-125">The first command gets the Notepad process and stores it in the $p variable.</span></span>

<span data-ttu-id="a86eb-126">Вторая команда использует параметр *ID* , третья команда использует параметр *Name* , а четвертая команда использует параметр *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="a86eb-126">The second command uses the *Id* parameter, the third command uses the *Name* parameter, and the fourth command uses the *InputObject* parameter.</span></span>

<span data-ttu-id="a86eb-127">Эти команды приводят к одинаковому результату и могут быть взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="a86eb-127">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="a86eb-128">Пример 3. Ожидание процессов в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="a86eb-128">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="a86eb-129">Эта команда 30 секунд ожидает окончания процессов Outlook и Winword.</span><span class="sxs-lookup"><span data-stu-id="a86eb-129">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span>
<span data-ttu-id="a86eb-130">Если оба процесса не остановлены, командлет отображает непрерывающую ошибку и командную строку.</span><span class="sxs-lookup"><span data-stu-id="a86eb-130">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="a86eb-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a86eb-131">PARAMETERS</span></span>

### <span data-ttu-id="a86eb-132">-Id</span><span class="sxs-lookup"><span data-stu-id="a86eb-132">-Id</span></span>

<span data-ttu-id="a86eb-133">Указывает идентификаторы процессов.</span><span class="sxs-lookup"><span data-stu-id="a86eb-133">Specifies the process IDs of the processes.</span></span>
<span data-ttu-id="a86eb-134">При указании нескольких идентификаторов разделяйте их запятыми.</span><span class="sxs-lookup"><span data-stu-id="a86eb-134">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="a86eb-135">Чтобы найти идентификатор процесса, введите `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="a86eb-135">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a86eb-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a86eb-136">-InputObject</span></span>

<span data-ttu-id="a86eb-137">Указывает процессы с помощью отправки объектов процессов.</span><span class="sxs-lookup"><span data-stu-id="a86eb-137">Specifies the processes by submitting process objects.</span></span>
<span data-ttu-id="a86eb-138">Введите переменную, которая содержит объекты процесса, или введите команду или выражение, которое получает объекты процесса, например командлет Get-Process.</span><span class="sxs-lookup"><span data-stu-id="a86eb-138">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the Get-Process cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a86eb-139">-Name</span><span class="sxs-lookup"><span data-stu-id="a86eb-139">-Name</span></span>

<span data-ttu-id="a86eb-140">Указывает имя процессов.</span><span class="sxs-lookup"><span data-stu-id="a86eb-140">Specifies the process names of the processes.</span></span>
<span data-ttu-id="a86eb-141">При указании нескольких имен разделяйте их запятыми.</span><span class="sxs-lookup"><span data-stu-id="a86eb-141">To specify multiple names, use commas to separate the names.</span></span>
<span data-ttu-id="a86eb-142">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a86eb-142">Wildcard characters are not supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a86eb-143">-Timeout</span><span class="sxs-lookup"><span data-stu-id="a86eb-143">-Timeout</span></span>

<span data-ttu-id="a86eb-144">Указывает максимальное время в секундах, в течение которого командлет ожидает завершения указанных процессов.</span><span class="sxs-lookup"><span data-stu-id="a86eb-144">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="a86eb-145">По истечении указанного времени команда отображает не прерывающую ошибку со списком еще выполняющихся процессов и завершает ожидание.</span><span class="sxs-lookup"><span data-stu-id="a86eb-145">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span>
<span data-ttu-id="a86eb-146">По умолчанию время ожидания отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a86eb-146">By default, there is no time-out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a86eb-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a86eb-147">CommonParameters</span></span>

<span data-ttu-id="a86eb-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a86eb-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a86eb-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a86eb-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a86eb-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a86eb-150">INPUTS</span></span>

### <span data-ttu-id="a86eb-151">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-151">System.Diagnostics.Process</span></span>

<span data-ttu-id="a86eb-152">Объект процесса можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a86eb-152">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="a86eb-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a86eb-153">OUTPUTS</span></span>

### <span data-ttu-id="a86eb-154">Нет</span><span class="sxs-lookup"><span data-stu-id="a86eb-154">None</span></span>

<span data-ttu-id="a86eb-155">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a86eb-155">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a86eb-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a86eb-156">NOTES</span></span>

<span data-ttu-id="a86eb-157">Командлет поддерживается только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="a86eb-157">The cmdlet is only supported on Windows platforms.</span></span>

<span data-ttu-id="a86eb-158">Этот командлет использует метод **ваитфорексит** класса **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="a86eb-158">This cmdlet uses the **WaitForExit** method of the **System.Diagnostics.Process** class.</span></span>

## <span data-ttu-id="a86eb-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a86eb-159">RELATED LINKS</span></span>

[<span data-ttu-id="a86eb-160">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-160">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="a86eb-161">Get-Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-161">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="a86eb-162">Start-Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-162">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="a86eb-163">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-163">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="a86eb-164">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="a86eb-164">Wait-Process</span></span>](Wait-Process.md)
