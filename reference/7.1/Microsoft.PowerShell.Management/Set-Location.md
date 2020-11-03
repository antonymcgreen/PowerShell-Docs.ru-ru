---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 0c511ea30d55c1e6949f687c81d1edef809546fc
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "93230450"
---
# <span data-ttu-id="7b0ee-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="7b0ee-103">Set-Location</span></span>

## <span data-ttu-id="7b0ee-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7b0ee-104">SYNOPSIS</span></span>
<span data-ttu-id="7b0ee-105">Присваивает текущему рабочему расположению указанное значение.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="7b0ee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b0ee-106">SYNTAX</span></span>

### <span data-ttu-id="7b0ee-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7b0ee-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="7b0ee-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7b0ee-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="7b0ee-109">Стек</span><span class="sxs-lookup"><span data-stu-id="7b0ee-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="7b0ee-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7b0ee-110">DESCRIPTION</span></span>

<span data-ttu-id="7b0ee-111">`Set-Location`Командлет задает рабочее расположение в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="7b0ee-112">Это расположение может быть каталогом, подкаталогом, расположением реестра или любым путем к поставщику.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="7b0ee-113">В PowerShell 6,2 добавлена поддержка `-` и `+` в качестве значений параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-113">PowerShell 6.2 added support for `-` and `+` as a values for the **Path** parameter.</span></span> <span data-ttu-id="7b0ee-114">PowerShell поддерживает журнал последних 20 расположений, к которым можно получить доступ с помощью `-` и `+` .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-114">PowerShell maintains a history of the last 20 locations that can be accessed with `-` and `+`.</span></span> <span data-ttu-id="7b0ee-115">Этот список не зависит от стека расположения, доступ к которому осуществляется с помощью параметра **StackName** .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-115">This list is independent from the location stack that is accessed using the **StackName** parameter.</span></span>

## <span data-ttu-id="7b0ee-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="7b0ee-116">EXAMPLES</span></span>

### <span data-ttu-id="7b0ee-117">Пример 1. Задание текущего расположения</span><span class="sxs-lookup"><span data-stu-id="7b0ee-117">Example 1: Set the current location</span></span>

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

<span data-ttu-id="7b0ee-118">Эта команда устанавливает текущее расположение в корневую папку `HKLM:` диска.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-118">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="7b0ee-119">Пример 2. Настройка текущего расположения и отображение этого расположения</span><span class="sxs-lookup"><span data-stu-id="7b0ee-119">Example 2: Set the current location and display that location</span></span>

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="7b0ee-120">Эта команда устанавливает текущее расположение в корневую папку `Env:` диска.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-120">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="7b0ee-121">Он использует параметр **PassThru** , чтобы направить PowerShell для возврата объекта **PathInfo** , представляющего `Env:\` расположение.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-121">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="7b0ee-122">Пример 3. Задание расположения для текущего расположения на диске C:</span><span class="sxs-lookup"><span data-stu-id="7b0ee-122">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="7b0ee-123">Первая команда задает расположение в качестве корня `HKLM:` диска в поставщике реестра.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-123">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="7b0ee-124">Вторая команда задает расположение текущего расположения `C:` диска в поставщике FileSystem.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-124">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="7b0ee-125">Если имя диска указано в форме `<DriveName>:` (без обратной косой черты), командлет задает расположение в текущем расположении в PSDrive.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-125">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="7b0ee-126">Чтобы получить текущее расположение в команде PSDrive use, выполните `Get-Location -PSDrive <DriveName>` команду.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-126">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="7b0ee-127">Пример 4. Установка текущего расположения в именованный стек</span><span class="sxs-lookup"><span data-stu-id="7b0ee-127">Example 4: Set the current location to a named stack</span></span>

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="7b0ee-128">Первая команда добавляет текущее расположение в стек путей.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-128">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="7b0ee-129">Вторая команда создает стек Locations Stack в текущем стеке расположения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-129">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="7b0ee-130">Третья команда отображает расположения в текущем стеке расположений.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-130">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="7b0ee-131">`*-Location`Командлеты используют текущий стек расположения, если в команде не указан другой стек расположения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-131">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="7b0ee-132">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-132">For information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="7b0ee-133">Пример 5. Навигация по журналу расположения с помощью `+` или `-`</span><span class="sxs-lookup"><span data-stu-id="7b0ee-133">Example 5: Navigate location history using `+` or `-`</span></span>

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

<span data-ttu-id="7b0ee-134">С помощью псевдонима `cd -` или `cd +` можно легко перемещаться по журналу расположения в терминале.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-134">Using the alias, `cd -` or `cd +` is an easy way to navigate through your location history while in your terminal.</span></span> <span data-ttu-id="7b0ee-135">Дополнительные сведения о переходе по см `-` / `+` . в разделе параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-135">For more information on navigating with `-`/`+`, see the **Path** parameter.</span></span>

## <span data-ttu-id="7b0ee-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7b0ee-136">PARAMETERS</span></span>

### <span data-ttu-id="7b0ee-137">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7b0ee-137">-LiteralPath</span></span>

<span data-ttu-id="7b0ee-138">Указывает путь к расположению.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-138">Specifies a path of the location.</span></span> <span data-ttu-id="7b0ee-139">Значение параметра **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-139">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="7b0ee-140">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-140">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="7b0ee-141">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-141">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7b0ee-142">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-142">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7b0ee-143">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7b0ee-143">-PassThru</span></span>

<span data-ttu-id="7b0ee-144">Возвращает объект **PathInfo** , представляющий расположение.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-144">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="7b0ee-145">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-145">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7b0ee-146">-Path</span><span class="sxs-lookup"><span data-stu-id="7b0ee-146">-Path</span></span>

<span data-ttu-id="7b0ee-147">Укажите путь к новому рабочему расположению.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-147">Specify the path of a new working location.</span></span> <span data-ttu-id="7b0ee-148">Если путь не указан, `Set-Location` по умолчанию используется домашний каталог текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-148">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="7b0ee-149">Если используются подстановочные знаки, командлет выбирает первый путь, соответствующий шаблону шаблона.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-149">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

<span data-ttu-id="7b0ee-150">PowerShell сохраняет историю последних 20 заданных расположений.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-150">PowerShell keeps a history of the last 20 locations you have set.</span></span> <span data-ttu-id="7b0ee-151">Если значение параметра **path** является `-` символом, новое рабочее расположение будет предыдущим рабочим расположением в журнале (если оно существует).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-151">If the **Path** parameter value is the `-` character, then the new working location will be the previous working location in history (if it exists).</span></span> <span data-ttu-id="7b0ee-152">Аналогично, если значение является `+` символом, новое рабочее расположение будет следующим рабочим расположением в журнале (если оно существует).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-152">Similarly, if the value is the `+` character, then the new working location will be the next working location in history (if it exists).</span></span> <span data-ttu-id="7b0ee-153">Это похоже на использование `Pop-Location` и `Push-Location` за исключением того, что журнал является списком, а не стеком и неявно отслеживанием, а не управляется вручную.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-153">This is similar to using `Pop-Location` and `Push-Location` except that the history is a list, not a stack, and is implicitly tracked, not manually controlled.</span></span> <span data-ttu-id="7b0ee-154">В настоящее время нет способа просмотреть список журналов.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-154">Currently, there is no way to view the history list.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="7b0ee-155">-StackName</span><span class="sxs-lookup"><span data-stu-id="7b0ee-155">-StackName</span></span>

<span data-ttu-id="7b0ee-156">Указывает существующее имя стека расположения, которое этот командлет делает текущим стеком расположения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-156">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="7b0ee-157">Введите имя стека папок.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-157">Enter a location stack name.</span></span> <span data-ttu-id="7b0ee-158">Чтобы указать неименованный стек расположения по умолчанию, введите `$null` или пустую строку ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-158">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="7b0ee-159">`*-Location`Командлеты действуют в текущем стеке, если не используется параметр **StackName** для указания другого стека.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-159">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span> <span data-ttu-id="7b0ee-160">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-160">For more information about location stacks, see the [Notes](#notes).</span></span>

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7b0ee-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7b0ee-161">CommonParameters</span></span>

<span data-ttu-id="7b0ee-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7b0ee-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7b0ee-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7b0ee-164">INPUTS</span></span>

### <span data-ttu-id="7b0ee-165">System.String</span><span class="sxs-lookup"><span data-stu-id="7b0ee-165">System.String</span></span>

<span data-ttu-id="7b0ee-166">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-166">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="7b0ee-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7b0ee-167">OUTPUTS</span></span>

### <span data-ttu-id="7b0ee-168">Нет, System. Management. Automation. PathInfo, System. Management. Automation. Пасинфостакк</span><span class="sxs-lookup"><span data-stu-id="7b0ee-168">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="7b0ee-169">Этот командлет не создает никаких выходных данных, если не указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-169">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="7b0ee-170">При использовании команды **PassThru** с **path** или **LiteralPath** создается объект **PathInfo** , представляющий новое расположение.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-170">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="7b0ee-171">Использование функции **PassThru** с **StackName** создает объект **пасинфостакк** , представляющий новый контекст стека.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-171">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="7b0ee-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7b0ee-172">NOTES</span></span>

<span data-ttu-id="7b0ee-173">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-173">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="7b0ee-174">Каждое пространство выполнения имеет свой собственный _текущий каталог_ .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-174">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="7b0ee-175">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-175">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="7b0ee-176">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-176">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="7b0ee-177">Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-177">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="7b0ee-178">Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-178">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="7b0ee-179">`Set-Location`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-179">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7b0ee-180">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-180">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="7b0ee-181">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="7b0ee-182">Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-182">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="7b0ee-183">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-183">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="7b0ee-184">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-184">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="7b0ee-185">PowerShell создает неименованный стек расположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-185">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="7b0ee-186">Можно создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-186">You can create multiple named location stacks.</span></span> <span data-ttu-id="7b0ee-187">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-187">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="7b0ee-188">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-188">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="7b0ee-189">Для управления стеками расположений используйте `*-Location` командлеты следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7b0ee-189">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="7b0ee-190">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-190">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="7b0ee-191">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-191">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="7b0ee-192">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-192">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="7b0ee-193">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** из `Get-Location` .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-193">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="7b0ee-194">Чтобы создать новый стек расположений, используйте параметр **StackName** из `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-194">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="7b0ee-195">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-195">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="7b0ee-196">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** из `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="7b0ee-196">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="7b0ee-197">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-197">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="7b0ee-198">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке.</span><span class="sxs-lookup"><span data-stu-id="7b0ee-198">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="7b0ee-199">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="7b0ee-199">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="7b0ee-200">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7b0ee-200">RELATED LINKS</span></span>

[<span data-ttu-id="7b0ee-201">Get-Location</span><span class="sxs-lookup"><span data-stu-id="7b0ee-201">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="7b0ee-202">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="7b0ee-202">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="7b0ee-203">Push-Location</span><span class="sxs-lookup"><span data-stu-id="7b0ee-203">Push-Location</span></span>](Push-Location.md)

