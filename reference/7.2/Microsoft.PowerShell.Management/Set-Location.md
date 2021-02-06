---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: ec6f69d1d4a0b382ceec26b9409d01501edb814f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604041"
---
# <span data-ttu-id="8564e-102">Set-Location</span><span class="sxs-lookup"><span data-stu-id="8564e-102">Set-Location</span></span>

## <span data-ttu-id="8564e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8564e-103">SYNOPSIS</span></span>
<span data-ttu-id="8564e-104">Присваивает текущему рабочему расположению указанное значение.</span><span class="sxs-lookup"><span data-stu-id="8564e-104">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="8564e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8564e-105">SYNTAX</span></span>

### <span data-ttu-id="8564e-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8564e-106">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="8564e-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8564e-107">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="8564e-108">Стек</span><span class="sxs-lookup"><span data-stu-id="8564e-108">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="8564e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8564e-109">DESCRIPTION</span></span>

<span data-ttu-id="8564e-110">`Set-Location`Командлет задает рабочее расположение в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="8564e-110">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="8564e-111">Это расположение может быть каталогом, подкаталогом, расположением реестра или любым путем к поставщику.</span><span class="sxs-lookup"><span data-stu-id="8564e-111">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="8564e-112">В PowerShell 6,2 добавлена поддержка `-` и `+` в качестве значений параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="8564e-112">PowerShell 6.2 added support for `-` and `+` as a values for the **Path** parameter.</span></span> <span data-ttu-id="8564e-113">PowerShell поддерживает журнал последних 20 расположений, к которым можно получить доступ с помощью `-` и `+` .</span><span class="sxs-lookup"><span data-stu-id="8564e-113">PowerShell maintains a history of the last 20 locations that can be accessed with `-` and `+`.</span></span> <span data-ttu-id="8564e-114">Этот список не зависит от стека расположения, доступ к которому осуществляется с помощью параметра **StackName** .</span><span class="sxs-lookup"><span data-stu-id="8564e-114">This list is independent from the location stack that is accessed using the **StackName** parameter.</span></span>

## <span data-ttu-id="8564e-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="8564e-115">EXAMPLES</span></span>

### <span data-ttu-id="8564e-116">Пример 1. Задание текущего расположения</span><span class="sxs-lookup"><span data-stu-id="8564e-116">Example 1: Set the current location</span></span>

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

<span data-ttu-id="8564e-117">Эта команда устанавливает текущее расположение в корневую папку `HKLM:` диска.</span><span class="sxs-lookup"><span data-stu-id="8564e-117">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="8564e-118">Пример 2. Настройка текущего расположения и отображение этого расположения</span><span class="sxs-lookup"><span data-stu-id="8564e-118">Example 2: Set the current location and display that location</span></span>

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="8564e-119">Эта команда устанавливает текущее расположение в корневую папку `Env:` диска.</span><span class="sxs-lookup"><span data-stu-id="8564e-119">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="8564e-120">Он использует параметр **PassThru** , чтобы направить PowerShell для возврата объекта **PathInfo** , представляющего `Env:\` расположение.</span><span class="sxs-lookup"><span data-stu-id="8564e-120">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="8564e-121">Пример 3. Задание расположения для текущего расположения на диске C:</span><span class="sxs-lookup"><span data-stu-id="8564e-121">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="8564e-122">Первая команда задает расположение в качестве корня `HKLM:` диска в поставщике реестра.</span><span class="sxs-lookup"><span data-stu-id="8564e-122">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="8564e-123">Вторая команда задает расположение текущего расположения `C:` диска в поставщике FileSystem.</span><span class="sxs-lookup"><span data-stu-id="8564e-123">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="8564e-124">Если имя диска указано в форме `<DriveName>:` (без обратной косой черты), командлет задает расположение в текущем расположении в PSDrive.</span><span class="sxs-lookup"><span data-stu-id="8564e-124">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="8564e-125">Чтобы получить текущее расположение в команде PSDrive use, выполните `Get-Location -PSDrive <DriveName>` команду.</span><span class="sxs-lookup"><span data-stu-id="8564e-125">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="8564e-126">Пример 4. Установка текущего расположения в именованный стек</span><span class="sxs-lookup"><span data-stu-id="8564e-126">Example 4: Set the current location to a named stack</span></span>

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

<span data-ttu-id="8564e-127">Первая команда добавляет текущее расположение в стек путей.</span><span class="sxs-lookup"><span data-stu-id="8564e-127">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="8564e-128">Вторая команда создает стек Locations Stack в текущем стеке расположения.</span><span class="sxs-lookup"><span data-stu-id="8564e-128">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="8564e-129">Третья команда отображает расположения в текущем стеке расположений.</span><span class="sxs-lookup"><span data-stu-id="8564e-129">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="8564e-130">`*-Location`Командлеты используют текущий стек расположения, если в команде не указан другой стек расположения.</span><span class="sxs-lookup"><span data-stu-id="8564e-130">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="8564e-131">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="8564e-131">For information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="8564e-132">Пример 5. Навигация по журналу расположения с помощью `+` или `-`</span><span class="sxs-lookup"><span data-stu-id="8564e-132">Example 5: Navigate location history using `+` or `-`</span></span>

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

<span data-ttu-id="8564e-133">С помощью псевдонима `cd -` или `cd +` можно легко перемещаться по журналу расположения в терминале.</span><span class="sxs-lookup"><span data-stu-id="8564e-133">Using the alias, `cd -` or `cd +` is an easy way to navigate through your location history while in your terminal.</span></span> <span data-ttu-id="8564e-134">Дополнительные сведения о переходе по см `-` / `+` . в разделе параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="8564e-134">For more information on navigating with `-`/`+`, see the **Path** parameter.</span></span>

## <span data-ttu-id="8564e-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8564e-135">PARAMETERS</span></span>

### <span data-ttu-id="8564e-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8564e-136">-LiteralPath</span></span>

<span data-ttu-id="8564e-137">Указывает путь к расположению.</span><span class="sxs-lookup"><span data-stu-id="8564e-137">Specifies a path of the location.</span></span> <span data-ttu-id="8564e-138">Значение параметра **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="8564e-138">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="8564e-139">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8564e-139">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="8564e-140">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8564e-140">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8564e-141">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="8564e-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="8564e-142">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8564e-142">-PassThru</span></span>

<span data-ttu-id="8564e-143">Возвращает объект **PathInfo** , представляющий расположение.</span><span class="sxs-lookup"><span data-stu-id="8564e-143">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="8564e-144">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8564e-144">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8564e-145">-Path</span><span class="sxs-lookup"><span data-stu-id="8564e-145">-Path</span></span>

<span data-ttu-id="8564e-146">Укажите путь к новому рабочему расположению.</span><span class="sxs-lookup"><span data-stu-id="8564e-146">Specify the path of a new working location.</span></span> <span data-ttu-id="8564e-147">Если путь не указан, `Set-Location` по умолчанию используется домашний каталог текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="8564e-147">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="8564e-148">Если используются подстановочные знаки, командлет выбирает первый путь, соответствующий шаблону шаблона.</span><span class="sxs-lookup"><span data-stu-id="8564e-148">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

<span data-ttu-id="8564e-149">PowerShell сохраняет историю последних 20 заданных расположений.</span><span class="sxs-lookup"><span data-stu-id="8564e-149">PowerShell keeps a history of the last 20 locations you have set.</span></span> <span data-ttu-id="8564e-150">Если значение параметра **path** является `-` символом, новое рабочее расположение будет предыдущим рабочим расположением в журнале (если оно существует).</span><span class="sxs-lookup"><span data-stu-id="8564e-150">If the **Path** parameter value is the `-` character, then the new working location will be the previous working location in history (if it exists).</span></span> <span data-ttu-id="8564e-151">Аналогично, если значение является `+` символом, новое рабочее расположение будет следующим рабочим расположением в журнале (если оно существует).</span><span class="sxs-lookup"><span data-stu-id="8564e-151">Similarly, if the value is the `+` character, then the new working location will be the next working location in history (if it exists).</span></span> <span data-ttu-id="8564e-152">Это похоже на использование `Pop-Location` и `Push-Location` за исключением того, что журнал является списком, а не стеком и неявно отслеживанием, а не управляется вручную.</span><span class="sxs-lookup"><span data-stu-id="8564e-152">This is similar to using `Pop-Location` and `Push-Location` except that the history is a list, not a stack, and is implicitly tracked, not manually controlled.</span></span> <span data-ttu-id="8564e-153">В настоящее время нет способа просмотреть список журналов.</span><span class="sxs-lookup"><span data-stu-id="8564e-153">Currently, there is no way to view the history list.</span></span>

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

### <span data-ttu-id="8564e-154">-StackName</span><span class="sxs-lookup"><span data-stu-id="8564e-154">-StackName</span></span>

<span data-ttu-id="8564e-155">Указывает существующее имя стека расположения, которое этот командлет делает текущим стеком расположения.</span><span class="sxs-lookup"><span data-stu-id="8564e-155">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="8564e-156">Введите имя стека папок.</span><span class="sxs-lookup"><span data-stu-id="8564e-156">Enter a location stack name.</span></span> <span data-ttu-id="8564e-157">Чтобы указать неименованный стек расположения по умолчанию, введите `$null` или пустую строку ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="8564e-157">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="8564e-158">`*-Location`Командлеты действуют в текущем стеке, если не используется параметр **StackName** для указания другого стека.</span><span class="sxs-lookup"><span data-stu-id="8564e-158">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span> <span data-ttu-id="8564e-159">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="8564e-159">For more information about location stacks, see the [Notes](#notes).</span></span>

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

### <span data-ttu-id="8564e-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8564e-160">CommonParameters</span></span>

<span data-ttu-id="8564e-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8564e-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8564e-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8564e-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8564e-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8564e-163">INPUTS</span></span>

### <span data-ttu-id="8564e-164">System.String</span><span class="sxs-lookup"><span data-stu-id="8564e-164">System.String</span></span>

<span data-ttu-id="8564e-165">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="8564e-165">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="8564e-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8564e-166">OUTPUTS</span></span>

### <span data-ttu-id="8564e-167">Нет, System. Management. Automation. PathInfo, System. Management. Automation. Пасинфостакк</span><span class="sxs-lookup"><span data-stu-id="8564e-167">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="8564e-168">Этот командлет не создает никаких выходных данных, если не указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="8564e-168">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="8564e-169">При использовании команды **PassThru** с **path** или **LiteralPath** создается объект **PathInfo** , представляющий новое расположение.</span><span class="sxs-lookup"><span data-stu-id="8564e-169">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="8564e-170">Использование функции **PassThru** с **StackName** создает объект **пасинфостакк** , представляющий новый контекст стека.</span><span class="sxs-lookup"><span data-stu-id="8564e-170">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="8564e-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8564e-171">NOTES</span></span>

<span data-ttu-id="8564e-172">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="8564e-172">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="8564e-173">Каждое пространство выполнения имеет свой собственный _текущий каталог_.</span><span class="sxs-lookup"><span data-stu-id="8564e-173">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="8564e-174">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="8564e-174">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="8564e-175">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="8564e-175">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="8564e-176">Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время.</span><span class="sxs-lookup"><span data-stu-id="8564e-176">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="8564e-177">Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="8564e-177">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="8564e-178">`Set-Location`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8564e-178">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8564e-179">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="8564e-179">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="8564e-180">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8564e-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="8564e-181">Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам.</span><span class="sxs-lookup"><span data-stu-id="8564e-181">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="8564e-182">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="8564e-182">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="8564e-183">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="8564e-183">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="8564e-184">PowerShell создает неименованный стек расположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8564e-184">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="8564e-185">Можно создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="8564e-185">You can create multiple named location stacks.</span></span> <span data-ttu-id="8564e-186">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="8564e-186">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="8564e-187">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="8564e-187">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="8564e-188">Для управления стеками расположений используйте `*-Location` командлеты следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8564e-188">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="8564e-189">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="8564e-189">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="8564e-190">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="8564e-190">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="8564e-191">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8564e-191">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="8564e-192">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** из `Get-Location` .</span><span class="sxs-lookup"><span data-stu-id="8564e-192">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="8564e-193">Чтобы создать новый стек расположений, используйте параметр **StackName** из `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="8564e-193">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="8564e-194">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="8564e-194">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="8564e-195">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** из `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="8564e-195">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="8564e-196">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="8564e-196">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="8564e-197">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке.</span><span class="sxs-lookup"><span data-stu-id="8564e-197">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="8564e-198">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="8564e-198">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="8564e-199">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8564e-199">RELATED LINKS</span></span>

[<span data-ttu-id="8564e-200">Get-Location</span><span class="sxs-lookup"><span data-stu-id="8564e-200">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="8564e-201">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="8564e-201">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="8564e-202">Push-Location</span><span class="sxs-lookup"><span data-stu-id="8564e-202">Push-Location</span></span>](Push-Location.md)

