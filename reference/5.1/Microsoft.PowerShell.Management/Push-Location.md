---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: abc40f3ae388a915c9df42d0c2df24f848e45e73
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "93230257"
---
# <span data-ttu-id="0ba25-103">Push-Location</span><span class="sxs-lookup"><span data-stu-id="0ba25-103">Push-Location</span></span>

## <span data-ttu-id="0ba25-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0ba25-104">SYNOPSIS</span></span>
<span data-ttu-id="0ba25-105">Добавляет текущее расположение в начало стека папок.</span><span class="sxs-lookup"><span data-stu-id="0ba25-105">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="0ba25-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ba25-106">SYNTAX</span></span>

### <span data-ttu-id="0ba25-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0ba25-107">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="0ba25-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ba25-108">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="0ba25-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ba25-109">DESCRIPTION</span></span>

<span data-ttu-id="0ba25-110">`Push-Location`Командлет добавляет ("отправляет") текущее расположение в стек расположений.</span><span class="sxs-lookup"><span data-stu-id="0ba25-110">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="0ba25-111">Если указать путь, `Push-Location` передает текущее расположение в стек, а затем меняет текущее расположение на расположение, указанное в пути.</span><span class="sxs-lookup"><span data-stu-id="0ba25-111">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="0ba25-112">`Pop-Location`Для получения расположений из стека расположений можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="0ba25-112">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="0ba25-113">По умолчанию `Push-Location` командлет отправляет текущее расположение в стек текущего расположения, но можно использовать параметр **StackName** для указания альтернативного стека расположения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-113">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="0ba25-114">Если стек не существует, `Push-Location` создает его.</span><span class="sxs-lookup"><span data-stu-id="0ba25-114">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="0ba25-115">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="0ba25-115">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="0ba25-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="0ba25-116">EXAMPLES</span></span>

### <span data-ttu-id="0ba25-117">Пример 1</span><span class="sxs-lookup"><span data-stu-id="0ba25-117">Example 1</span></span>

<span data-ttu-id="0ba25-118">Этот пример отправляет текущее расположение в стек папок по умолчанию, а затем изменяет расположение на `C:\Windows` .</span><span class="sxs-lookup"><span data-stu-id="0ba25-118">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="0ba25-119">Пример 2</span><span class="sxs-lookup"><span data-stu-id="0ba25-119">Example 2</span></span>

<span data-ttu-id="0ba25-120">Этот пример отправляет текущее расположение в стек Регфунктион и изменяет текущее расположение на `HKLM:\Software\Policies` расположение.</span><span class="sxs-lookup"><span data-stu-id="0ba25-120">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="0ba25-121">Командлеты Location можно использовать на любом диске PowerShell (PSDrive).</span><span class="sxs-lookup"><span data-stu-id="0ba25-121">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="0ba25-122">Пример 3</span><span class="sxs-lookup"><span data-stu-id="0ba25-122">Example 3</span></span>

<span data-ttu-id="0ba25-123">Эта команда помещает текущее расположение в стек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0ba25-123">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="0ba25-124">Она не меняет расположение.</span><span class="sxs-lookup"><span data-stu-id="0ba25-124">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="0ba25-125">Пример 4. Создание и использование именованного стека</span><span class="sxs-lookup"><span data-stu-id="0ba25-125">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="0ba25-126">Эти команды показывают, как создавать и использовать именованные стеки папок.</span><span class="sxs-lookup"><span data-stu-id="0ba25-126">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="0ba25-127">Первая команда помещает текущее расположение в новый стек с именем Stack2, а затем изменяет текущее расположение на корневой каталог, представленный в команде символом тильды ( `~` ), который при использовании на дисках поставщика файловой системы эквивалентен `$HOME` и `$env:USERPROFILE` .</span><span class="sxs-lookup"><span data-stu-id="0ba25-127">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="0ba25-128">Если Stack2 еще не существует в сеансе, `Push-Location` создает его.</span><span class="sxs-lookup"><span data-stu-id="0ba25-128">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="0ba25-129">Вторая команда использует `Pop-Location` командлет для POP в исходное расположение ( `C:\` ) из стека Stack2.</span><span class="sxs-lookup"><span data-stu-id="0ba25-129">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="0ba25-130">Без параметра **StackName** `Pop-Location` будет вытолкнуть расположение из неименованного стека по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0ba25-130">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="0ba25-131">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="0ba25-131">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="0ba25-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ba25-132">PARAMETERS</span></span>

### <span data-ttu-id="0ba25-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ba25-133">-LiteralPath</span></span>

<span data-ttu-id="0ba25-134">Указывает путь к новому расположению.</span><span class="sxs-lookup"><span data-stu-id="0ba25-134">Specifies the path to the new location.</span></span> <span data-ttu-id="0ba25-135">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="0ba25-135">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="0ba25-136">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="0ba25-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0ba25-137">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="0ba25-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0ba25-138">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="0ba25-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0ba25-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0ba25-139">-PassThru</span></span>

<span data-ttu-id="0ba25-140">Передает объект, представляющий расположение, по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="0ba25-140">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="0ba25-141">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="0ba25-141">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ba25-142">-Path</span><span class="sxs-lookup"><span data-stu-id="0ba25-142">-Path</span></span>

<span data-ttu-id="0ba25-143">Добавляет текущее расположение в начало стека и заменяет это расположение на указанное данным путем.</span><span class="sxs-lookup"><span data-stu-id="0ba25-143">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="0ba25-144">Введите путь к любому расположению, поставщик которого поддерживает данный командлет.</span><span class="sxs-lookup"><span data-stu-id="0ba25-144">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="0ba25-145">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0ba25-145">Wildcards are permitted.</span></span> <span data-ttu-id="0ba25-146">Имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0ba25-146">The parameter name is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0ba25-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="0ba25-147">-StackName</span></span>

<span data-ttu-id="0ba25-148">Указывает стек папок, в который будет добавлено текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="0ba25-148">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="0ba25-149">Введите имя стека папок.</span><span class="sxs-lookup"><span data-stu-id="0ba25-149">Enter a location stack name.</span></span>
<span data-ttu-id="0ba25-150">Если стек не существует, `Push-Location` создает его.</span><span class="sxs-lookup"><span data-stu-id="0ba25-150">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="0ba25-151">Без этого параметра `Push-Location` добавляет расположение в текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-151">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="0ba25-152">По умолчанию текущий стек расположений — это безымянный стек расположения по умолчанию, создаваемый PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ba25-152">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="0ba25-153">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="0ba25-153">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="0ba25-154">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="0ba25-154">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="0ba25-155">`Push-Location` невозможно добавить расположение в неименованный стек по умолчанию, если он не является текущим стеком расположения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-155">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0ba25-156">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="0ba25-156">-UseTransaction</span></span>

<span data-ttu-id="0ba25-157">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0ba25-157">Includes the command in the active transaction.</span></span> <span data-ttu-id="0ba25-158">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="0ba25-158">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="0ba25-159">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md).</span><span class="sxs-lookup"><span data-stu-id="0ba25-159">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ba25-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0ba25-160">CommonParameters</span></span>

<span data-ttu-id="0ba25-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0ba25-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ba25-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0ba25-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ba25-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0ba25-163">INPUTS</span></span>

### <span data-ttu-id="0ba25-164">System.String</span><span class="sxs-lookup"><span data-stu-id="0ba25-164">System.String</span></span>

<span data-ttu-id="0ba25-165">Строку, содержащую путь (но не литеральный путь), можно передать в `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="0ba25-165">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="0ba25-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0ba25-166">OUTPUTS</span></span>

### <span data-ttu-id="0ba25-167">None или System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="0ba25-167">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="0ba25-168">При использовании параметра **PassThru** `Push-Location` создает объект **System. Management. Automation. PathInfo** , представляющий расположение.</span><span class="sxs-lookup"><span data-stu-id="0ba25-168">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="0ba25-169">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0ba25-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0ba25-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0ba25-170">NOTES</span></span>

<span data-ttu-id="0ba25-171">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="0ba25-171">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="0ba25-172">Каждое пространство выполнения имеет свой собственный _текущий каталог_ .</span><span class="sxs-lookup"><span data-stu-id="0ba25-172">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="0ba25-173">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="0ba25-173">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="0ba25-174">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="0ba25-174">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="0ba25-175">Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время.</span><span class="sxs-lookup"><span data-stu-id="0ba25-175">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="0ba25-176">Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-176">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="0ba25-177">Стек — это последний список, в котором доступен только последний добавленный элемент.</span><span class="sxs-lookup"><span data-stu-id="0ba25-177">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="0ba25-178">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="0ba25-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="0ba25-179">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="0ba25-179">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="0ba25-180">PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-180">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="0ba25-181">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-181">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="0ba25-182">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="0ba25-182">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="0ba25-183">Для управления стеками расположений используйте командлеты расположения PowerShell, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="0ba25-183">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="0ba25-184">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="0ba25-184">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="0ba25-185">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="0ba25-185">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="0ba25-186">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="0ba25-186">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="0ba25-187">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="0ba25-187">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="0ba25-188">Чтобы создать новый стек расположений, используйте параметр StackName `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="0ba25-188">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="0ba25-189">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="0ba25-189">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="0ba25-190">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр StackName `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="0ba25-190">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="0ba25-191">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="0ba25-191">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="0ba25-192">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке.</span><span class="sxs-lookup"><span data-stu-id="0ba25-192">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="0ba25-193">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="0ba25-193">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="0ba25-194">Также можно ссылаться `Push-Location` по встроенному псевдониму `pushd` .</span><span class="sxs-lookup"><span data-stu-id="0ba25-194">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="0ba25-195">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="0ba25-195">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="0ba25-196">`Push-Location`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0ba25-196">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0ba25-197">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="0ba25-197">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="0ba25-198">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0ba25-198">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0ba25-199">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0ba25-199">RELATED LINKS</span></span>

[<span data-ttu-id="0ba25-200">Get-Location</span><span class="sxs-lookup"><span data-stu-id="0ba25-200">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="0ba25-201">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="0ba25-201">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="0ba25-202">Set-Location</span><span class="sxs-lookup"><span data-stu-id="0ba25-202">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="0ba25-203">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="0ba25-203">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="0ba25-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0ba25-204">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)