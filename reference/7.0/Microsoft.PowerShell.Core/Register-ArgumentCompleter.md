---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: 0e0b5fcd99372d699bd6250383adc85b3a5f8847
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225945"
---
# <span data-ttu-id="dc94d-103">Register-ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="dc94d-103">Register-ArgumentCompleter</span></span>

## <span data-ttu-id="dc94d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dc94d-104">SYNOPSIS</span></span>

<span data-ttu-id="dc94d-105">Регистрирует пользовательский аргумент для завершения.</span><span class="sxs-lookup"><span data-stu-id="dc94d-105">Registers a custom argument completer.</span></span>

## <span data-ttu-id="dc94d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dc94d-106">SYNTAX</span></span>

### <span data-ttu-id="dc94d-107">Собственный</span><span class="sxs-lookup"><span data-stu-id="dc94d-107">NativeSet</span></span>

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### <span data-ttu-id="dc94d-108">PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc94d-108">PowerShellSet</span></span>

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="dc94d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dc94d-109">DESCRIPTION</span></span>

<span data-ttu-id="dc94d-110">`Register-ArgumentCompleter`Командлет регистрирует пользовательский аргумент Complete.</span><span class="sxs-lookup"><span data-stu-id="dc94d-110">The `Register-ArgumentCompleter` cmdlet registers a custom argument completer.</span></span> <span data-ttu-id="dc94d-111">Завершение аргумента позволяет обеспечить динамическое завершение табуляции во время выполнения любой указанной команды.</span><span class="sxs-lookup"><span data-stu-id="dc94d-111">An argument completer allows you to provide dynamic tab completion, at run time for any command that you specify.</span></span>

## <span data-ttu-id="dc94d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="dc94d-112">EXAMPLES</span></span>

### <span data-ttu-id="dc94d-113">Пример 1. Регистрация пользовательского аргумента Complete</span><span class="sxs-lookup"><span data-stu-id="dc94d-113">Example 1: Register a custom argument completer</span></span>

<span data-ttu-id="dc94d-114">В следующем примере выполняется регистрация завершения аргумента для параметра **ID** `Set-TimeZone` командлета.</span><span class="sxs-lookup"><span data-stu-id="dc94d-114">The following example registers an argument completer for the **Id** parameter of the `Set-TimeZone` cmdlet.</span></span>

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

<span data-ttu-id="dc94d-115">Первая команда создает блок скрипта, который принимает обязательные параметры, которые передаются при нажатии клавиши <kbd>Tab</kbd>пользователем. Дополнительные сведения см. в описании параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="dc94d-115">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="dc94d-116">В блоке скрипта доступные значения для **идентификатора** извлекаются с помощью `Get-TimeZone` командлета.</span><span class="sxs-lookup"><span data-stu-id="dc94d-116">Within the script block, the available values for **Id** are retrieved using the `Get-TimeZone` cmdlet.</span></span> <span data-ttu-id="dc94d-117">Свойство **ID** для каждого часового пояса передается в `Where-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="dc94d-117">The **Id** property for each Time Zone is piped to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="dc94d-118">`Where-Object`Командлет фильтрует все идентификаторы, которые не начинаются со значения, предоставленного параметром `$wordToComplete` , который представляет текст, введенный пользователем до нажатия клавиши <kbd>Tab</kbd>. Отфильтрованные идентификаторы передаются в `For-EachObject` командлет, который заключает каждое значение в кавычки, если значение содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="dc94d-118">The `Where-Object` cmdlet filters out any ids that do not start with the value provided by `$wordToComplete`, which represents the text the user typed before they pressed <kbd>Tab</kbd>. The filtered ids are piped to the `For-EachObject` cmdlet which encloses each value in quotes, should the value contain spaces.</span></span>

<span data-ttu-id="dc94d-119">Вторая команда регистрирует завершенный аргумент, передавая ScriptBlock, **идентификатор** **ParameterName** и **CommandName** `Set-TimeZone` .</span><span class="sxs-lookup"><span data-stu-id="dc94d-119">The second command registers the argument completer by passing the scriptblock, the **ParameterName** **Id** and the **CommandName** `Set-TimeZone`.</span></span>

### <span data-ttu-id="dc94d-120">Пример 2. Добавление сведений к значениям заполнения нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="dc94d-120">Example 2: Add details to your tab completion values</span></span>

<span data-ttu-id="dc94d-121">Следующий пример перезаписывает заполнение клавиши TAB для параметра **Name** `Stop-Service` командлета и возвращает только выполняющиеся службы.</span><span class="sxs-lookup"><span data-stu-id="dc94d-121">The following example overwrites tab completion for the **Name** parameter of the `Stop-Service` cmdlet and only returns running services.</span></span>

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

<span data-ttu-id="dc94d-122">Первая команда создает блок скрипта, который принимает обязательные параметры, которые передаются при нажатии клавиши <kbd>Tab</kbd>пользователем. Дополнительные сведения см. в описании параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="dc94d-122">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="dc94d-123">В блоке скрипта первая команда извлекает все работающие службы с помощью `Where-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="dc94d-123">Within the script block, the first command retrieves all running services using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="dc94d-124">Службы передаются в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="dc94d-124">The services are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="dc94d-125">`ForEach-Object`Командлет создает новый объект [System. Management. Automation. комплетионресулт](/dotnet/api/system.management.automation.completionresult) и заполняет его именем текущей службы (представленной переменной конвейера `$_.Name` ).</span><span class="sxs-lookup"><span data-stu-id="dc94d-125">The `ForEach-Object` cmdlet creates a new [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) object and populates it with the name of the current service (represented by the pipeline variable `$_.Name`).</span></span>

<span data-ttu-id="dc94d-126">Объект **комплетионресулт** позволяет предоставить дополнительные сведения для каждого возвращаемого значения:</span><span class="sxs-lookup"><span data-stu-id="dc94d-126">The **CompletionResult** object allows you to provide additional details to each returned value:</span></span>

- <span data-ttu-id="dc94d-127">**комплетионтекст** (строка) — текст, используемый в качестве результата автоматического завершения.</span><span class="sxs-lookup"><span data-stu-id="dc94d-127">**completionText** (String) - The text to be used as the auto completion result.</span></span> <span data-ttu-id="dc94d-128">Это значение, отправляемое команде.</span><span class="sxs-lookup"><span data-stu-id="dc94d-128">This is the value sent to the command.</span></span>
- <span data-ttu-id="dc94d-129">**листитемтекст** (строка) — текст, отображаемый в списке, например, когда пользователь нажимает клавишу <kbd>CTRL</kbd> + <kbd>пробел</kbd>.</span><span class="sxs-lookup"><span data-stu-id="dc94d-129">**listItemText** (String) - The text to be displayed in a list, such as when the user presses <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span> <span data-ttu-id="dc94d-130">Используется только для вывода и не передается команде, если она выбрана.</span><span class="sxs-lookup"><span data-stu-id="dc94d-130">This is used for display only and is not passed to the command when selected.</span></span>
- <span data-ttu-id="dc94d-131">**resultType** ( [комплетионресулттипе](/dotnet/api/system.management.automation.completionresulttype)) — тип результата завершения.</span><span class="sxs-lookup"><span data-stu-id="dc94d-131">**resultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) - The type of completion result.</span></span>
- <span data-ttu-id="dc94d-132">**ToolTip** (строка) — текст подсказки с подробными сведениями о объекте.</span><span class="sxs-lookup"><span data-stu-id="dc94d-132">**toolTip** (String) - The text for the tooltip with details to be displayed about the object.</span></span>
  <span data-ttu-id="dc94d-133">Это видно, когда пользователь выбирает элемент после нажатия клавиши <kbd>CTRL</kbd> + <kbd>Space</kbd>.</span><span class="sxs-lookup"><span data-stu-id="dc94d-133">This is visible when the user selects an item after pressing <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span>

<span data-ttu-id="dc94d-134">Последняя команда показывает, что остановленные службы по-прежнему могут передаваться в `Stop-Service` командлет вручную.</span><span class="sxs-lookup"><span data-stu-id="dc94d-134">The last command demonstrates that stopped services can still be passed in manually to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="dc94d-135">Заполнение нажатием клавиши Tab является единственным аспектом.</span><span class="sxs-lookup"><span data-stu-id="dc94d-135">The tab completion is the only aspect affected.</span></span>

### <span data-ttu-id="dc94d-136">Пример 3. Регистрация собственного собственного аргумента Complete</span><span class="sxs-lookup"><span data-stu-id="dc94d-136">Example 3: Register a custom Native argument completer</span></span>

<span data-ttu-id="dc94d-137">Можно использовать **собственный** параметр, чтобы обеспечить завершение клавиши TAB для собственной команды.</span><span class="sxs-lookup"><span data-stu-id="dc94d-137">You can use the **Native** parameter to provide tab-completion for a native command.</span></span> <span data-ttu-id="dc94d-138">В следующем примере показано добавление заполнения клавишей TAB для `dotnet` интерфейса командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="dc94d-138">The following example adds tab-completion for the `dotnet` Command Line Interface (CLI).</span></span>

> [!NOTE]
> <span data-ttu-id="dc94d-139">`dotnet complete`Команда доступна только в версии 2,0 и более поздних версиях CLI DotNet.</span><span class="sxs-lookup"><span data-stu-id="dc94d-139">The `dotnet complete` command is only available in version 2.0 and greater of the dotnet cli.</span></span>

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

<span data-ttu-id="dc94d-140">Первая команда создает блок скрипта, который принимает обязательные параметры, которые передаются при нажатии клавиши <kbd>Tab</kbd>пользователем. Дополнительные сведения см. в описании параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="dc94d-140">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="dc94d-141">В блоке скрипта `dotnet complete` команда используется для выполнения заполнения нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="dc94d-141">Within the script block, the `dotnet complete` command is used to perform the tab completion.</span></span>
<span data-ttu-id="dc94d-142">Результаты передаются в `ForEach-Object` командлет, который использует **Новый** статический метод класса [System. Management. Automation. комплетионресулт](/dotnet/api/system.management.automation.completionresult) для создания нового объекта **комплетионресулт** для каждого значения.</span><span class="sxs-lookup"><span data-stu-id="dc94d-142">The results are piped to the `ForEach-Object` cmdlet which use the **new** static method of the [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) class to create a new **CompletionResult** object for each value.</span></span>

## <span data-ttu-id="dc94d-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dc94d-143">PARAMETERS</span></span>

### <span data-ttu-id="dc94d-144">-CommandName</span><span class="sxs-lookup"><span data-stu-id="dc94d-144">-CommandName</span></span>

<span data-ttu-id="dc94d-145">Задает имя команд в виде массива.</span><span class="sxs-lookup"><span data-stu-id="dc94d-145">Specifies the name of the commands as an array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc94d-146">— Native</span><span class="sxs-lookup"><span data-stu-id="dc94d-146">-Native</span></span>

<span data-ttu-id="dc94d-147">Указывает, что завершение аргумента предназначено для собственной команды, где PowerShell не может завершить имена параметров.</span><span class="sxs-lookup"><span data-stu-id="dc94d-147">Indicates that the argument completer is for a native command where PowerShell cannot complete parameter names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc94d-148">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="dc94d-148">-ParameterName</span></span>

<span data-ttu-id="dc94d-149">Указывает имя параметра, аргумент которого завершается.</span><span class="sxs-lookup"><span data-stu-id="dc94d-149">Specifies the name of the parameter whose argument is being completed.</span></span> <span data-ttu-id="dc94d-150">Указанное имя параметра не может быть перечислимым значением, например параметром **ForegroundColor** `Write-Host` командлета.</span><span class="sxs-lookup"><span data-stu-id="dc94d-150">The parameter name specified cannot be an enumerated value, such as the **ForegroundColor** parameter of the `Write-Host` cmdlet.</span></span>

<span data-ttu-id="dc94d-151">Дополнительные сведения о перечислениях см. в разделе [about_Enum](./About/about_Enum.md).</span><span class="sxs-lookup"><span data-stu-id="dc94d-151">For more information on enums, see [about_Enum](./About/about_Enum.md).</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc94d-152">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="dc94d-152">-ScriptBlock</span></span>

<span data-ttu-id="dc94d-153">Задает команды, выполняемые для выполнения заполнения нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="dc94d-153">Specifies the commands to run to perform tab completion.</span></span> <span data-ttu-id="dc94d-154">Предоставленный блок скрипта должен возвращать значения, которые завершают входные данные.</span><span class="sxs-lookup"><span data-stu-id="dc94d-154">The script block you provide should return the values that complete the input.</span></span> <span data-ttu-id="dc94d-155">Блок скрипта должен выполнять девращение значений с помощью конвейера ( `ForEach-Object` , `Where-Object` и т. д.) или другого подходящего метода.</span><span class="sxs-lookup"><span data-stu-id="dc94d-155">The script block must unroll the values using the pipeline (`ForEach-Object`, `Where-Object`, etc.), or another suitable method.</span></span> <span data-ttu-id="dc94d-156">Возврат массива значений приводит к тому, что PowerShell обрабатывает весь массив как **одно** значение заполнения Tab.</span><span class="sxs-lookup"><span data-stu-id="dc94d-156">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="dc94d-157">Блок скрипта должен принимать следующие параметры в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="dc94d-157">The script block must accept the following parameters in the order specified below.</span></span> <span data-ttu-id="dc94d-158">Имена параметров не важны, так как PowerShell передает значения по положению.</span><span class="sxs-lookup"><span data-stu-id="dc94d-158">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="dc94d-159">`$commandName` (Расположение 0) — Этот параметр задает имя команды, для которой блок скрипта обеспечивает заполнение нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="dc94d-159">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="dc94d-160">`$parameterName` (Расположение 1) — Этот параметр задан для параметра, значение которого требует заполнения нажатием клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="dc94d-160">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="dc94d-161">`$wordToComplete` (Расположение 2) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="dc94d-161">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="dc94d-162">`$commandAst` (Расположение 3) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки.</span><span class="sxs-lookup"><span data-stu-id="dc94d-162">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="dc94d-163">Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="dc94d-163">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="dc94d-164">`$fakeBoundParameters` (Расположение 4) — для этого параметра задается хэш-таблица `$PSBoundParameters` , содержащая для командлета перед нажатием пользователем <kbd>вкладки</kbd>. Дополнительные сведения см. в разделе [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="dc94d-164">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span></span>

<span data-ttu-id="dc94d-165">При указании **собственного** параметра блок скрипта должен принимать следующие параметры в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="dc94d-165">When you specify the **Native** parameter, the script block must take the following parameters in the specified order.</span></span> <span data-ttu-id="dc94d-166">Имена параметров не важны, так как PowerShell передает значения по положению.</span><span class="sxs-lookup"><span data-stu-id="dc94d-166">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="dc94d-167">`$wordToComplete` (Расположение 0) — Этот параметр имеет значение, указанное пользователем до нажатия клавиши <kbd>Tab</kbd>. Блок скрипта должен использовать это значение для определения значений заполнения клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="dc94d-167">`$wordToComplete` (Position 0) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="dc94d-168">`$commandAst` (Расположение 1) — Этот параметр имеет значение дерево абстрактного синтаксиса (AST) для текущей входной строки.</span><span class="sxs-lookup"><span data-stu-id="dc94d-168">`$commandAst` (Position 1) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="dc94d-169">Дополнительные сведения см. в разделе [класс AST](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="dc94d-169">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="dc94d-170">`$cursorPosition` (Расположение 2) — Этот параметр задает позицию курсора при нажатии пользователем <kbd>вкладки</kbd>.</span><span class="sxs-lookup"><span data-stu-id="dc94d-170">`$cursorPosition` (Position 2) - This parameter is set to the position of the cursor when the user pressed <kbd>Tab</kbd>.</span></span>

<span data-ttu-id="dc94d-171">В качестве атрибута параметра можно также указать **аргументкомплетер** .</span><span class="sxs-lookup"><span data-stu-id="dc94d-171">You can also provide an **ArgumentCompleter** as a parameter attribute.</span></span> <span data-ttu-id="dc94d-172">Дополнительные сведения см. в разделе [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="dc94d-172">For more information, see [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc94d-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dc94d-173">CommonParameters</span></span>

<span data-ttu-id="dc94d-174">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dc94d-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dc94d-175">См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="dc94d-175">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dc94d-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dc94d-176">INPUTS</span></span>

### <span data-ttu-id="dc94d-177">Нет</span><span class="sxs-lookup"><span data-stu-id="dc94d-177">None</span></span>

<span data-ttu-id="dc94d-178">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="dc94d-178">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="dc94d-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dc94d-179">OUTPUTS</span></span>

### <span data-ttu-id="dc94d-180">Нет</span><span class="sxs-lookup"><span data-stu-id="dc94d-180">None</span></span>

<span data-ttu-id="dc94d-181">Этот командлет не возвращает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="dc94d-181">This cmdlet returns no output.</span></span>

## <span data-ttu-id="dc94d-182">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dc94d-182">NOTES</span></span>

## <span data-ttu-id="dc94d-183">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dc94d-183">RELATED LINKS</span></span>
